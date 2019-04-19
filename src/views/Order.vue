<template lang="pug">
  v-form#nativeForm(method='post', action='http://localhost:3000/products', v-model='valid')
    v-text-field(label='コード', v-model='code', :rules='codeRules', :counter='6', required='', name='code')
    v-text-field(label='名称', v-model='name', :rules='nameRules', :counter='30', required='', name='name')
    v-text-field(label='フリガナ', v-model='furigana', name='furigana')
    v-text-field(label='単位', v-model='unit', name='unit')
    v-text-field(label='入数', v-model='in_number', name='in_number')
    v-text-field(label='規格・型番', v-model='standard', name='standard')
    v-text-field(label='色', v-model='color', name='color')
    v-text-field(label='サイズ', v-model='size', name='size')
    v-text-field(label='数量小数桁', v-model='quantity_small_number_digits', name='quantity_small_number_digits')
    v-text-field(label='単価小数桁', v-model='unit_price_small_number_digits', name='unit_price_small_number_digits')
    v-text-field(label='課税区分', v-model='taxed_kubun', name='taxed_kubun')
    v-text-field(label='在庫管理', v-model='inventory_control', name='inventory_control')
    v-text-field(label='発注ロット', v-model='order_lot', name='order_lot')
    v-text-field(label='リードタイム', v-model='read_time', name='read_time')
    v-text-field(label='在庫適正数', v-model='inventory_appropriate_number', name='inventory_appropriate_number')
    v-text-field(label='在庫評価方法', v-model='inventory_evaluation_method', name='inventory_evaluation_method')
    v-text-field(label='主たる仕入先', v-model='supplier_id', name='supplier_id')
    v-text-field(label='主たる倉庫', v-model='warehouse_id', name='warehouse_id')
    v-text-field(label='現在庫数', v-model='current_stock_number', name='current_stock_number')
    v-text-field(label='最終出庫日', v-model='last_issuing_date', name='last_issuing_date')
    v-text-field(label='最終入庫日', v-model='last_receiving_date', name='last_receiving_date')
    v-text-field(label='上代', v-model='retail_price', name='retail_price')
    v-text-field(label='売上単価１', v-model='sales_unit_price1', name='sales_unit_price1')
    v-text-field(label='売上単価２', v-model='sales_unit_price2', name='sales_unit_price2')
    v-text-field(label='売上単価３', v-model='sales_unit_price3', name='sales_unit_price3')
    v-text-field(label='売上単価４', v-model='sales_unit_price4', name='sales_unit_price4')
    v-text-field(label='売上原価', v-model='sales_cost', name='sales_cost')
    v-text-field(label='仕入単価', v-model='purchase_unit_price', name='purchase_unit_price')
    v-text-field(label='標準原価', v-model='standard_cost', name='standard_cost')
    v-text-field(label='分類', v-model='category_id', name='category_id')
    v-text-field(label='参照表示', v-model='reference_display', name='reference_display')
    v-text-field(label='メモ欄', v-model='memo', name='memo')
    v-text-field(label='更新日', v-model='updated_date', name='updated_date')
    // v-text-field(label='E-mail', v-model='email', :rules='emailRules', required='', name='mail')
    v-btn(@click='submit', :disabled='!valid') 登録
</template>

 <script>
    export default {
      name: 'contact',

      data () {
         return { 
            valid: false,
            code: '',
            codeRules: [
              (v) => !!v || 'コードを入力して下さい。',
              (v) => v.length <= 6 || 'コードは6文字以下で入力して下さい。'
            ],
            name: '',
            nameRules: [
              (v) => !!v || '名称を入力して下さい。',
              (v) => v.length <= 30 || '名称は30文字以下で入力して下さい。'
            ],
            // email: '',
            // emailRules: [
            //   (v) => !!v || 'メールアドレスを入力して下さい。',
            //   (v) => /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(v) || 'メールアドレスが不正です。'
            // ]
          }
        },
        methods: {
          submit() {
            nativeForm.submit()
          }
        }
      }
  </script>