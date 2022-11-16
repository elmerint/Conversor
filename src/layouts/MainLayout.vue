<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar class="bg-deep-purple">
        

        <q-toolbar-title>
          Conversor
        </q-toolbar-title>

        
      </q-toolbar>
    </q-header>

    
    <q-page-container>
      <div class="q-pa-md" style="max-width: 400px">

      <div class="text-h5">
        Conversión de coordenadas WG84 a Proyección canónica
      </div>
    
      <q-input
        filled
        v-model="gradosN"
        label="Grados"
        lazy-rules
        :rules="[val => val && val.length > 0 || 'Pleas type something']"
      />
      {{minutosN}}
      <q-input
        filled
        
        v-model="minutosN"
        label="Minutos"
        lazy-rules
        
      />
      <q-input
        filled
        
        v-model="segundosN"
        label="Segundos"
        
        
      />
      <q-input
        filled
        
        v-model="gradosW"
        label="Grados"
        
        
      />
      <q-input
        filled
        v-model="minutosW"
        label="Minutos"
      />
      <q-input
        filled
        v-model="segundosW"
        label="Segundos"
        
        
      />
      <q-input
      v-model="result1"
      />

      <div>
        <q-btn label="Submit" type="submit" color="primary"/>
        <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
    

  </div>
    </q-page-container>
  </q-layout>
</template>

<script>



export default {
  name: 'MainLayout',
  data () {
    return {
      gradosN:'',
      minutosN:'',
      segundosN:'',
      gradosW:'',
      minutosW:'',
      segundosW:'',
      result1
    }
  },
  methods: {
    converUno () {
      if(gradosN.isNaN || minutosN.isNaN || segundosN.isNaN || gradosW.isNaN || minutosW.isNaN || segundosW.isNaN){
           this.$q.notify({
            color: 'red-5',
            textColor: 'white',
            icon: 'warning',
            message: 'Debes llenar todos los campos'
        })
      }else{
        result1=gradosW*segundosW+minutosW
      }
    },

    onReset () {
      // gradosN='',
      // minutosN='',
      // segundosN='',
      // gradosW='',
      // minutosW='',
      // segundosW=''
    }
  }
}

</script>
