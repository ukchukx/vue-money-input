<template>
  <!-- eslint-disable -->
  <masked-input type="text" v-model="amount" :mask="currencyMask" :guide="false" />
</template>
<script>
import MaskedInput from 'vue-text-mask';
import createNumberMask from 'text-mask-addons/dist/createNumberMask';

const normalizeAmount = (x) => x || x == 0 ? `${x}` : '';

export default {
  name: 'MoneyInput',
  components: {
    MaskedInput
  },
  props: {
    initialAmount: {
      type: Number,
      default: () => 0
    },
    currencySymbol: {
      type: String,
      default: () => '₦'
    }
  },
  data() {
    return {
      amount: normalizeAmount(this.initialAmount)
    };
  },
  computed: {
    currencyMask() {
      return createNumberMask({ prefix: this.currencySymbol, allowDecimal: true });
    }
  },
  watch: {
    amount(str) {
      const regex = new RegExp(`[${this.currencySymbol},]`, 'g');
      this.$emit('input', str.length ? parseFloat(str.replace(regex, '')) : 0);
    },
    initialAmount(newAmount) {
      this.amount = normalizeAmount(newAmount);
    }
  }
};
</script>

