
<script >
const Calcular = {
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
    },
  },
};

export default Calcular;
</script>