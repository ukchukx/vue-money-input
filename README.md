# vue-money-input

A Vue component for inputting monetary amounts.

## Installation

```js
npm i -S @ukchukx/vue-money-input
```

### Browser

```html
<script type="text/javascript" src="https://unpkg.com/vue"></script>
<script type="text/javascript" src="https://unpkg.com/@ukchukx/vue-money-input"></script>
<script type="text/javascript">
  Vue.use(MoneyInput);
</script>
```

### Module

```js
import MoneyInput from '@ukchukx/vue-money-input';
```

## Usage

Once installed, it can be used in a template as simply as:

```html
<money-input :initial-amount="initialAmount" v-model="amount" />
```

Or styled as a Bootstrap input:

```html
<money-input class="form-control" :initial-amount="initialAmount" v-model="amount" />
```

The currency prefix can be changed:

```html
<money-input currency-symbol="$" :initial-amount="initialAmount" v-model="amount" />
```
