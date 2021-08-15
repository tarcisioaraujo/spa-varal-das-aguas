<template>
  <div>
        <div class="modal fade" id="modalExemplo" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
          <div class="modal-dialog" role="document">
            <div class="modal-content">
              <div class="modal-header">
                <h5 class="modal-title" id="exampleModalLabel">Cadastro</h5>
                <button type="button" class="close" data-dismiss="modal" aria-label="Fechar">
                  <span aria-hidden="true">&times;</span>
                </button>
              </div>
              <div class="modal-body">                
                <div class="alert alert-success" style="display: none;" id="success-alert">
                  <button type="button" class="close" data-dismiss="alert">x</button>
                  Inscrição realizada com sucesso.
                </div>
                <div class="alert alert-danger" style="display: none;" id="danger-alert">
                  <button type="button" class="close" data-dismiss="alert">x</button>
                  Houve um problema ao fazer sua inscrição.
                </div>
                <form>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                            <label for="inputName4">Nome do colaborador:</label>
                            <input type="text" class="form-control" id="inputName4" placeholder="Insira seu nome" v-model="inscricao.nome">
                        </div>
                        <div class="form-group col-md-6">
                            <label for="inputNamePhoto4">Nome da foto:</label>
                            <input type="text" class="form-control" id="inputNamePhoto4" placeholder="Insira o nome da foto" v-model="inscricao.nome_foto">
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                            <label for="inputNameLacation4">Local da foto:</label>
                            <input type="text" class="form-control" id="inputNameLacation4" placeholder="Insira o local da foto" v-model="inscricao.local_foto">
                        </div>
                        <div class="form-group col-md-6">
                            <label for="inputDate4">Data de registro:</label>
                            <input type="text" class="form-control" id="inputDate4" placeholder="MM/DD/YYYY" v-model="inscricao.data_foto">
                        </div>
                    </div>
                    <div class="form-group">
                        <label for="photoFile1">Anexar foto</label>
                        <input type="file" class="form-control-file" id="photoFile1" @change="processFile($event)">
                    </div>
                    <div class="form-group">
                        <label for="terms">Termos</label>
                        <textarea class="form-control" id="terms" rows="4" placeholder="" required>I. Onoaneoan oeaneonao na&#10;&#10;II. Onon nonon onnonon&#10;&#10;III. Ono nono nono nono non on nonon Onon&#10;&#10;IV. Onon onononono nonon o&#10;&#10;
                        </textarea>
                    </div>                  
                    <div class="form-group">
                        <div class="form-check">
                            <input class="form-check-input" type="checkbox" value="" id="invalidCheck2" v-model="inscricao.termos" required>
                            <label class="form-check-label" for="invalidCheck2">
                                Eu li e concordo com os termos
                            </label>
                        </div>
                    </div>                                        
                </form>
              </div>
              <div class="modal-footer">                
                <button type="button" class="btn btn-primary" v-on:click="processSubscribe()">Enviar</button>
              </div>
            </div>
          </div>
        </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'SubscriptionModal',
  data () {
    return {
      inscricao:{
        nome:'',
        nome_foto:'',
        local_foto:'',
        data_foto:'',
        fileImage:'',
        termos:false
      }
    }
  },
  methods:{
    processFile(e) {
      this.inscricao.fileImage = e.target.files[0]
      if (!this.inscricao.fileImage) {
        return
      }      
    },    
    convertFileImageToBase64(file) {
      return new Promise((resolve, reject) => {
        const reader = new FileReader();
        reader.readAsDataURL(file);
        reader.onload = () => resolve(reader.result.split(',')[1]);
        reader.onerror = error => reject(error);
      });
    },
    sendSubscribe() {      
      // return axios.post('http://apidev.inema.ba.gov.br/participante', {
      //   nome: this.inscricao.nome,
      //   nome_foto: this.inscricao.nome_foto,
      //   local_foto: this.inscricao.local_foto,
      //   data_foto: this.inscricao.data_foto,
      //   img_base64: this.inscricao.fileImage,
      //   termos: this.inscricao.termos        
      // });
      return Promise.resolve('Success')
    },
    async processSubscribe(){ 
      var vm = this 
      this.convertFileImageToBase64(this.inscricao.fileImage)
      .then(function (imgBase64) {        
        vm.inscricao.fileImage = imgBase64
        return vm.sendSubscribe()                       
      })  
      .then(function (response) {        
        $('#success-alert').show();
        $('#danger-alert').hide();
        return
      })    
      .catch(function (error) {                
        $('#danger-alert').show();
        $('#success-alert').hide();
        return
      });

      

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
