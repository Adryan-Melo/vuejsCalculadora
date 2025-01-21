<script >
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: '+',
    };
  },
  computed: {
    resultado() {
      let n1 = parseFloat(this.numero1);
      let n2 = parseFloat(this.numero2);

      switch (this.operacao) {
        case '+':
          return n1 + n2;
        case '-':
          return n1 - n2;
        case '*':
          return n1 * n2;
        case '/':
          return n2 !== 0 ? n1 / n2 : 'Divisão por zero!';
        default:
          return 0;
      }
    }
  }
};
</script>

<template>
  <div id="app" class="calculadora">
    <h1>Calculadora</h1>

    
    <input type="number" v-model="numero1" placeholder="Digite o primeiro número" />
    
     
        <select v-model="operacao">
          <option value="+">Adicionar (+)</option>
          <option value="-">Subtrair (-)</option>
          <option value="*">Multiplicar (*)</option>
          <option value="/">Dividir (/)</option>
        </select>

    <input type="number" v-model="numero2" placeholder="Digite o segundo número" />

   
    <div class="resultado">
      Resultado: {{ resultado }}
    </div>
  </div>
</template>

<style >
body {
  font-family: 'Arial', sans-serif;
  background-color: #f4f7fc; 
  color: #333;
  text-align: center;
  padding: 40px 0;
  margin: 0;
}


.calculadora {
  max-width: 400px;
  width: 100%;
  margin: 0 auto;
  background: #ffffff;
  padding: 20px;
  border-radius: 15px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}


h1 {
  font-size: 32px;
  color: #2c3e50;
  margin-bottom: 20px;
  font-weight: 600;
}

input, select {
  width: 90%;
  padding: 16px;
  margin: 8px 0;
  font-size: 16px;
  border: 2px solid #3498db; 
  border-radius: 8px;
  outline: none;
  transition: border-color 0.3s;
}

input:focus, select:focus {
  border-color: #2980b9; 
}


input:hover, select:hover {
  border-color: #2980b9;
}

select {
  background-color: #ecf4fd; 
}


.resultado {
  font-size: 24px;
  font-weight: bold;
  color: #2c3e50;
  margin-top: 20px;
  padding: 15px;
  background-color: #ecf4fd; 
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}


@media (max-width: 768px) {
  .calculadora {
    padding: 15px;
  }

  h1 {
    font-size: 28px;
  }

  input, select {
    font-size: 14px;
    padding: 14px;
  }
}

@media (max-width: 480px) {
  .calculadora {
    padding: 12px;
  }

  h1 {
    font-size: 24px;
  }

  input, select {
    font-size: 12px;
    padding: 12px;
  }

  .resultado {
    font-size: 18px;
    padding: 12px;
  }
}

</style>
