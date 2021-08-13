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
                <form>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                            <label for="inputName4">Nome do colaborador:</label>
                            <input type="name" class="form-control" id="inputName4" placeholder="Insira seu nome">
                        </div>
                        <div class="form-group col-md-6">
                            <label for="inputNamePhoto4">Nome da foto:</label>
                            <input type="name" class="form-control" id="inputNamePhoto4" placeholder="Insira o nome da foto">
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                            <label for="inputNameLacation4">Local da foto:</label>
                            <input type="name" class="form-control" id="inputNameLacation4" placeholder="Insira o local da foto">
                        </div>
                        <div class="form-group col-md-6">
                            <label for="inputDate4">Data de registro:</label>
                            <input type="name" class="form-control" id="inputDate4" placeholder="MM/DD/YYYY">
                        </div>
                    </div>
                    <div class="form-group">
                        <label for="photoFile1">Anexar foto</label>
                        <input type="file" class="form-control-file" id="photoFile1">
                    </div>
                    <div class="form-group">
                        <label for="terms">Termos</label>
                        <textarea class="form-control" id="terms" rows="4" placeholder="" required>I. Onoaneoan oeaneonao na&#10;&#10;II. Onon nonon onnonon&#10;&#10;III. Ono nono nono nono non on nonon Onon&#10;&#10;IV. Onon onononono nonon o&#10;&#10;
                        </textarea>
                    </div>                  
                    <div class="form-group">
                        <div class="form-check">
                            <input class="form-check-input" type="checkbox" value="" id="invalidCheck2" required>
                            <label class="form-check-label" for="invalidCheck2">
                                Eu li e concordo com os termos
                            </label>
                        </div>
                    </div>                    
                    <button type="submit" class="btn btn-primary">Entrar</button>
                </form>
              </div>
              <div class="modal-footer">
                <button type="button" class="btn btn-secondary" data-dismiss="modal">Fechar</button>
                <button type="button" class="btn btn-primary">Salvar mudanças</button>
              </div>
            </div>
          </div>
        </div>
  </div>
</template>

<script>
export default {
  name: 'SubscriptionModal',
  data () {
    return {
      
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
