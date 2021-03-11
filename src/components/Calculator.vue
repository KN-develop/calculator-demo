<template>
  <div class="calculator">
    <div class="calculator i-bem calculator_js_inited" data-bem="{&quot;calculator&quot;:{}}" data-log-node="dvbk39">
      <div class="calculator__wrapper">
        <div class="calculator__screen">
          <span
              class="radio-button radio-button_theme_custom radio-button_view_classic calculator__switcher i-bem radio-button_js_inited"
              data-bem="{&quot;radio-button&quot;:{&quot;live&quot;:false}}" data-log-node="dvbk3a" v-if="this.prev && this.operation">
            {{this.prev}}&nbsp;{{this.operation}}
          </span>

          <div class="calculator-display calculator-display_hidden_yes i-bem calculator-display_js_inited"
               data-bem="{&quot;calculator-display&quot;:{}}" data-log-node="dvbk3d">
            <div class="calculator-display__error">Ошибка</div>
            <div class="calculator-display__output"><span class="calculator-display__input-string"></span><span
                class="link link_pseudo_yes link_inner_yes link_theme_normal calculator-display__link i-bem link_js_inited"
                data-bem="{&quot;link&quot;:{}}" data-log-node="dvbk3e" tabindex="0" role="button"><div
                class="calculator-display__input-link"></div></span><span
                class="calculator-display__equal"> = </span><span class="calculator-display__result"></span></div>
            <span class="calculator-display__infinity">∞</span></div>
          <span
              class="input input_size_s input_browser_chrome input_inputmode_numeric input_empty_yes input_theme_normal i-bem input_js_inited"
              data-bem="{&quot;input&quot;:{&quot;live&quot;:false}}" data-log-node="dvbk3f"><span
              class="input__box"><span class="input__clear" unselectable="on" role="button" aria-hidden="true"
                                       data-log-node="dvbk3g">&nbsp;</span><input class="input__control"
                                                                                  id="uniq161545248692433988" name=""
                                                                                  placeholder="0" value=""
                                                                                  aria-labelledby="labeluniq161545248692433988 hintuniq161545248692433988"
                                                                                  data-log-node="dvbk3h"
                                                                                  readonly
                                                                                  :value="input || 0"
                                                                                  :class="{'disabled-full': !input}"
                                                                                  style="width: 100%; pointer-events: none"></span></span>
        </div>
        <div class="calculator__btns clearfix">
          <div class="calculator__row">
            <button
                class="disabled-full button2 button2_size_m button2_theme_default button2_type_advanced button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_m i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3i"><span
                class="button2__text">x<span
                class="calculator__sup">y</span></span></button>
            <button
                class="disabled-full button2 button2_size_m button2_theme_default button2_type_advanced button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_m i-bem button2_js_inited"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3j"><span
                class="button2__text">x!</span></button>
            <button
                class="disabled-full button2 button2_size_m button2_theme_default button2_type_advanced button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_m i-bem button2_js_inited"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3k"><span
                class="button2__text">±</span></button>
            <button
                @click="clear"
                class="button2 button2_size_m button2_theme_default button2_type_casual button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_m i-bem button2_js_inited"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3l"><span
                class="button2__text">C</span></button>
            <button
                class="disabled-full button2 button2_size_m button2_theme_default button2_type_casual button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_s i-bem button2_js_inited"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3m"><span
                class="button2__text">( )</span></button>
            <button
                class="disabled-full button2 button2_size_m button2_theme_default button2_type_casual button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_s i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3n"><span
                class="button2__text">%</span></button>
            <button
                @click="calculate('/')"
                class="button2 button2_size_m button2_theme_default button2_type_primary button2_subtype_medium button2_view_classic calculator__btn calculator__btn_size_l i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3o"><span
                class="button2__text">÷</span></button>
          </div>
          <div class="calculator__row">
            <button
                class="disabled-full disabled-full button2 button2_size_m button2_theme_default button2_type_advanced button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_s i-bem button2_js_inited"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3p"><span
                class="button2__text">asin</span></button>
            <button
                class="disabled-full disabled-full button2 button2_size_m button2_theme_default button2_type_advanced button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_s i-bem button2_js_inited"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3q"><span
                class="button2__text">sin</span></button>
            <button
                class="disabled-full disabled-full button2 button2_size_m button2_theme_default button2_type_advanced button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_s i-bem button2_js_inited"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3r"><span
                class="button2__text">1/x</span></button>
            <button
                @click="addInput(7)"
                class="button2 button2_size_m button2_theme_default button2_type_casual button2_subtype_big button2_view_classic calculator__btn calculator__btn_size_m i-bem button2_js_inited"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3s"><span
                class="button2__text">7</span></button>
            <button
                @click="addInput(8)"
                class="button2 button2_size_m button2_theme_default button2_type_casual button2_subtype_big button2_view_classic calculator__btn calculator__btn_size_m i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3t"><span
                class="button2__text">8</span></button>
            <button
                @click="addInput(9)"
                class="button2 button2_size_m button2_theme_default button2_type_casual button2_subtype_big button2_view_classic calculator__btn calculator__btn_size_m i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3u"><span
                class="button2__text">9</span></button>
            <button
                @click="calculate('*')"
                class="button2 button2_size_m button2_theme_default button2_type_primary button2_subtype_medium button2_view_classic calculator__btn calculator__btn_size_l i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3v"><span
                class="button2__text">×</span></button>
          </div>
          <div class="calculator__row">
            <button
                class="disabled-full button2 button2_size_m button2_theme_default button2_type_advanced button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_s i-bem button2_js_inited"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3w"><span
                class="button2__text">acos</span></button>
            <button
                class="disabled-full button2 button2_size_m button2_theme_default button2_type_advanced button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_s i-bem button2_js_inited"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3x"><span
                class="button2__text">cos</span></button>
            <button
                class="disabled-full button2 button2_size_m button2_theme_default button2_type_advanced button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_s i-bem button2_js_inited"
                data-bem="{&quot;button2&quot;:{},&quot;calculator__btn&quot;:{&quot;action&quot;:&quot;cmd&quot;,&quot;arg&quot;:&quot;√&quot;}}"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3y"><span
                class="button2__text">√</span></button>
            <button
                @click="addInput(4)"
                class="button2 button2_size_m button2_theme_default button2_type_casual button2_subtype_big button2_view_classic calculator__btn calculator__btn_size_m i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk3z"><span
                class="button2__text">4</span></button>
            <button
                @click="addInput(5)"
                class="button2 button2_size_m button2_theme_default button2_type_casual button2_subtype_big button2_view_classic calculator__btn calculator__btn_size_m i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk40"><span
                class="button2__text">5</span></button>
            <button
                @click="addInput(6)"
                class="button2 button2_size_m button2_theme_default button2_type_casual button2_subtype_big button2_view_classic calculator__btn calculator__btn_size_m i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk41"><span
                class="button2__text">6</span></button>
            <button
                @click="calculate('-')"
                class="button2 button2_size_m button2_theme_default button2_type_primary button2_subtype_medium button2_view_classic calculator__btn calculator__btn_size_l i-bem button2_js_inited"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk42"><span
                class="button2__text">−</span></button>
          </div>
          <div class="calculator__row">
            <button
                class="disabled-full button2 button2_size_m button2_theme_default button2_type_advanced button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_s i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk43"><span
                class="button2__text">atan</span></button>
            <button
                class="disabled-full button2 button2_size_m button2_theme_default button2_type_advanced button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_s i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk44"><span
                class="button2__text">tan</span></button>
            <button
                class="disabled-full button2 button2_size_m button2_theme_default button2_type_advanced button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_s i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk45"><span
                class="button2__text">ln</span></button>
            <button
                @click="addInput(1)"
                class="button2 button2_size_m button2_theme_default button2_type_casual button2_subtype_big button2_view_classic calculator__btn calculator__btn_size_m i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk46"><span
                class="button2__text">1</span></button>
            <button
                @click="addInput(2)"
                class="button2 button2_size_m button2_theme_default button2_type_casual button2_subtype_big button2_view_classic calculator__btn calculator__btn_size_m i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk47"><span
                class="button2__text">2</span></button>
            <button
                @click="addInput(3)"
                class="button2 button2_size_m button2_theme_default button2_type_casual button2_subtype_big button2_view_classic calculator__btn calculator__btn_size_m i-bem button2_js_inited"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk48"><span
                class="button2__text">3</span></button>
            <button
                @click="calculate('+')"
                class="button2 button2_size_m button2_theme_default button2_type_primary button2_subtype_medium button2_view_classic calculator__btn calculator__btn_size_l i-bem button2_js_inited"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk49"><span
                class="button2__text">+</span></button>
          </div>
          <div class="calculator__row">
            <button
                class="disabled-full button2 button2_size_m button2_theme_default button2_type_advanced button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_s i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk4a"><span
                class="button2__text">lg</span></button>
            <button
                class="disabled-full button2 button2_size_m button2_theme_default button2_type_advanced button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_s i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk4b"><span
                class="button2__text">π</span></button>
            <button
                class="disabled-full button2 button2_size_m button2_theme_default button2_type_advanced button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_s i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk4c"><span
                class="button2__text">e</span></button>
            <button
                @click="addInput(0)"
                class="button2 button2_size_m button2_theme_default button2_type_casual button2_subtype_bigwide button2_view_classic calculator__btn calculator__btn_size_m i-bem button2_js_inited"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk4d"><span
                class="button2__text">0</span></button>
            <button
                @click="addInput('.')"
                class="button2 button2_size_m button2_theme_default button2_type_casual button2_subtype_normal button2_view_classic calculator__btn calculator__btn_size_m i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk4e"><span
                class="button2__text">,</span></button>
            <button
                @click="calculate('=')"
                class="button2 button2_size_m button2_theme_default button2_type_primary button2_subtype_medium button2_view_classic calculator__btn calculator__btn_size_l i-bem"
                type="button" autocomplete="off" tabindex="0" data-log-node="dvbk4f"><span
                class="button2__text">=</span></button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
const OPERATIONS = {
  '+': (prev, cur) => (prev + cur),
  '-': (prev, cur) => (prev - cur),
  '*': (prev, cur) => (prev * cur),
  '/': (prev, cur) => (prev / cur),
};

export default {
  data() {
    return {
      input: '',
      prev: '',
      operation: '',
    }
  },
  methods: {
    addInput(number) {
      if (!this.prev && this.operation) {
        this.prev = this.input;
        this.input = '';
      }
      this.input = [...this.input, number].join('');
    },

    clear() {
      if (!this.input) {
        this.operation = '';
        this.prev = '';
      }
      this.input = '';
    },

    calculate(operation) {
      if (!this.prev) {
        this.prev = this.input;
        this.input = '';
      }

      if (operation === '=' || (this.operation && this.input)) {
        console.log('operation');
        const handler = OPERATIONS[this.operation];
        console.log({handler, operation});
        this.operation = operation !== '=' ? operation : '';

        if (handler) {
          const res = handler(Number.parseFloat(this.prev), Number.parseFloat(this.input) || 0);
          console.log({res, ts: res.toString()});
          this.input = res.toString();
          this.prev = '';
        }
      }


      if (operation !== '=') {
        this.operation = operation;
      }
    }
  }
}
</script>

<style scoped>
.disabled-full {
  pointer-events: none !important;
  opacity: 0.3 !important;
}

body .calculator {
  position: relative
}

body .calculator .calculator__control_size_m {
  padding-top: 10px;
  font-size: 36px;
  line-height: 36px
}

body .calculator .calculator__control_size_s {
  padding-top: 19px;
  font-size: 24px;
  line-height: 36px
}

body .calculator .calculator__control_size_xs {
  padding-top: 22px;
  font-size: 20px;
  line-height: 20px
}

body .calculator__wrapper {
  box-sizing: border-box;
  width: 533px;
  border: 1px solid #bfbfbf;
  border-radius: 4px;
  background: #bfbfbf
}

body .calculator__screen {
  position: relative;
  border-bottom: 1px solid #bfbfbf;
  border-top-left-radius: 3px;
  border-top-right-radius: 3px;
  background: #fff
}

body .calculator .input {
  display: block
}

body .calculator .input__control {
  height: 60px;
  padding: 0 24px 12px;
  font-size: 48px;
  line-height: 48px;
  text-align: right;
  color: #000
}

body .calculator .input_browser_safari .input__control {
  line-height: 60px
}

body .calculator .input_browser_firefox .input__control {
  position: relative;
  top: 6px;
  height: 70px;
  margin-top: -10px
}

body .calculator .input_browser_firefox .calculator__control_size_m {
  top: 5px
}

body .calculator .input_browser_firefox .calculator__control_size_s, body .calculator .input_browser_firefox .calculator__control_size_xs {
  top: 4px
}

body .calculator .input.input_theme_normal .input__box::before {
  border: 0
}

body .calculator .input.input_theme_normal .input__control {
  border: 0
}

body .calculator .input__box {
  overflow: hidden;
  padding-right: 0
}

body .calculator .input__hint {
  right: 24px;
  height: 60px;
  margin-top: -1px;
  padding-right: 0;
  font-size: 48px;
  line-height: 48px;
  text-align: right
}

.i-ua_js_no .calculator[class] .input, .i-ua_js_no .calculator__btns, body .calculator .input__clear {
  display: none
}

.i-ua_js_no .calculator[class] {
  height: auto
}

.calculator[class] .input_browser_edge.input_empty_yes .input__control {
  direction: rtl
}

body .calculator__sup {
  position: relative;
  top: -8px;
  font-size: 13px;
  vertical-align: top
}

body .calculator__row {
  margin-bottom: 1px;
  white-space: nowrap
}

body .calculator__row:last-child {
  margin-bottom: 0;
  border-bottom-right-radius: 3px;
  border-bottom-left-radius: 3px
}

body .calculator__row:last-child .calculator__btn:first-child, body .calculator__row:last-child .calculator__btn:first-child::before {
  border-bottom-left-radius: 3px
}

body .calculator__row:last-child .calculator__btn:last-child, body .calculator__row:last-child .calculator__btn:last-child::before {
  border-bottom-right-radius: 3px
}

body .calculator__btn.button2 {
  position: relative;
  display: inline-block;
  width: 75px;
  height: 48px;
  margin: 0 1px 0 0;
  vertical-align: top;
  outline: 0;
  transition: transform .1s linear;
  transition: transform .1s linear, -webkit-transform .1s linear;
  -webkit-tap-highlight-color: transparent
}

body .calculator__btn.button2, body .calculator__btn.button2::before {
  border: 0;
  border-radius: 0;
  background: #fff
}

body .calculator__btn.button2.button2_view_classic::before {
  border-width: 2px;
  border-color: transparent
}

body .calculator__btn.button2.button2_focused_yes::before {
  border-style: solid
}

body .calculator__btn.button2 .button2__text {
  padding: 0;
  font-size: 18px;
  line-height: 38px;
  color: #000
}

body .calculator__btn.button2.button2_type_casual, body .calculator__btn.button2.button2_type_casual.button2_pressed_yes, body .calculator__btn.button2.button2_type_casual.button2_pressed_yes::before, body .calculator__btn.button2.button2_type_casual::before {
  color: #000;
  background: #fff
}

body .calculator__btn.button2.button2_type_advanced, body .calculator__btn.button2.button2_type_advanced::before {
  background: #ebebeb
}

body .calculator__btn.button2.button2_type_advanced.button2_pressed_yes, body .calculator__btn.button2.button2_type_advanced.button2_pressed_yes::before {
  color: #000;
  background: #ebebeb
}

body .calculator__btn.button2.button2_type_advanced::before {
  content: ''
}

body .calculator__btn.button2.button2_type_primary {
  margin-right: 0;
  box-shadow: 1px 1px 0 #d1a700, -1px -1px 0 #d1a700, 1px -1px 0 #d1a700, -1px 1px 0 #d1a700
}

body .calculator__btn.button2.button2_type_primary, body .calculator__btn.button2.button2_type_primary::before {
  background: #fc0
}

body .calculator__btn.button2.button2_type_primary.button2_pressed_yes, body .calculator__btn.button2.button2_type_primary.button2_pressed_yes::before {
  color: #000;
  border-color: #d1a700;
  background: #fc0
}

body .calculator__btn.button2.button2_type_primary.button2_hovered_yes, body .calculator__btn.button2.button2_type_primary:hover {
  border-color: #d1a700
}

body .calculator__btn.button2.button2_type_primary .button2__text {
  display: inline-block;
  width: 36px;
  line-height: 41px;
  border-radius: 18px
}

body .calculator__btn.button2.button2_subtype_medium .button2__text {
  font-size: 21px
}

body .calculator__btn.button2.button2_subtype_normal .button2__text {
  font-size: 18px
}

body .calculator__btn.button2.button2_subtype_bigwide {
  width: 151px;
  text-align: left
}

body .calculator__btn.button2.button2_subtype_bigwide .button2__text {
  width: 49px;
  margin: 0 13px;
  text-align: center
}

body .calculator__btn.button2.button2_subtype_bigwide.button2_hovered_yes .button2__text, body .calculator__btn.button2.button2_subtype_bigwide:hover .button2__text {
  margin: 0 13px
}

body .calculator__btn.button2.button2_hovered_yes::after, body .calculator__btn.button2:hover::after {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  content: '';
  background: rgba(0, 0, 0, .05)
}

body .calculator__btn.button2.button2_focused_yes, body .calculator__btn.button2.button2_pressed_yes {
  -webkit-transform: scale(.96);
  transform: scale(.96)
}

.calculator__switcher {
  position: absolute;
  z-index: 10;
  top: 16px;
  left: 24px;
  font-size: 14px;
  font-weight: 700;
  line-height: 18px;
  white-space: nowrap;
  letter-spacing: .6px;
  text-transform: uppercase;
  color: #999
}

.i-ua_js_no .calculator__switcher {
  display: none
}

.calculator__switcher .radio-button__radio_checked_yes, .calculator__switcher .radio-button__radio_pressed_yes {
  color: #000;
  border-bottom: 2px solid #000;
  border-radius: 0
}

.calculator__switcher .radio-button__text {
  padding: 0
}

.calculator__switcher .radio-button__divider {
  display: inline-block;
  vertical-align: top
}

.calculator__switcher .radio-button__divider::before {
  content: ' · '
}

.calculator_broken_yes .input input {
  position: absolute;
  right: 0;
  width: 999px
}

.calculator_broken_yes.calculator .input__box {
  overflow: visible;
  height: 60px
}

.calculator_broken_yes .calculator__row:last-child .calculator__btn:last-child, .calculator_broken_yes .calculator__row:last-child .calculator__btn:last-child::before {
  background-color: #639
}

.calculator-display {
  overflow: hidden;
  height: 28px;
  margin-left: 80px;
  padding: 10px 24px;
  font-size: 18px;
  line-height: 28px;
  text-align: right;
  color: #999
}

.i-ua_js_no .calculator-display_hidden_yes {
  visibility: hidden
}

.calculator-display__error, .calculator-display__output {
  display: none;
  overflow: hidden;
  padding-left: 30px;
  white-space: nowrap
}

.i-ua_js_no .calculator-display__output {
  display: block
}

.calculator-display__infinity {
  position: relative;
  top: 4px;
  display: none;
  font-size: 26px;
  line-height: 20px
}

.calculator-display__link {
  outline: 0
}

.calculator-display__input-link, .calculator-display__input-string {
  overflow: hidden;
  max-width: 200px;
  vertical-align: bottom;
  white-space: nowrap;
  text-decoration: none;
  text-overflow: ellipsis;
  border-bottom: 0
}

.calculator-display__input-link {
  display: none
}

.calculator-display__input-string, .calculator-display__output_clickable_yes .calculator-display__input-link {
  display: inline-block
}

.calculator-display__output_clickable_yes .calculator-display__input-string {
  display: none
}

.calculator-display__sup {
  position: relative;
  top: -8px;
  vertical-align: middle
}

.clearfix:after {
  display: block;
  clear: both;
  height: 0;
  content: ''
}

.input_size_s {
  font-size: 13px;
  line-height: 28px
}

.input_size_s .input__control, .input_size_s .input__hint {
  height: 28px;
  border-right-width: 8px;
  border-left-width: 8px
}

.input_size_s .input__icon {
  width: 28px
}

.input_size_s .input__clear {
  width: 28px;
  height: 28px
}

.input_size_s .input__icon_side_right ~ .input__clear {
  right: 14px
}

.input_size_s .input__clear_visibility_visible ~ .input__control {
  border-right-width: 22px
}

.input_size_s .input__icon_side_right ~ .input__clear_visibility_visible ~ .input__control {
  border-right-width: 36px
}

.input_size_s .input__hint.input__hint_rpad_yes, .input_size_s .input__icon_side_right ~ .input__control {
  border-right-width: 28px
}

.input_size_s .input__hint.input__hint_lpad_yes, .input_size_s .input__icon_side_left ~ .input__control {
  border-left-width: 28px
}

.input_size_s.input_type_textarea .input__control {
  padding: 4px 6px 0
}

.input_size_s.input_type_textarea .input__clear ~ .input__control {
  padding-right: 22px
}

.input_size_s .input__control {
  line-height: 28px
}

.input_size_m {
  font-size: 15px;
  line-height: 32px
}

.input_size_m .input__control, .input_size_m .input__hint {
  height: 32px;
  border-right-width: 10px;
  border-left-width: 10px
}

.input_size_m .input__icon {
  width: 32px
}

.input_size_m .input__clear {
  width: 32px;
  height: 32px
}

.input_size_m .input__icon_side_right ~ .input__clear {
  right: 16px
}

.input_size_m .input__clear_visibility_visible ~ .input__control {
  border-right-width: 26px
}

.input_size_m .input__icon_side_right ~ .input__clear_visibility_visible ~ .input__control {
  border-right-width: 42px
}

.input_size_m .input__hint.input__hint_rpad_yes, .input_size_m .input__icon_side_right ~ .input__control {
  border-right-width: 32px
}

.input_size_m .input__hint.input__hint_lpad_yes, .input_size_m .input__icon_side_left ~ .input__control {
  border-left-width: 32px
}

.input_size_m.input_type_textarea .input__control {
  padding: 6px 8px 0
}

.input_size_m.input_type_textarea .input__clear ~ .input__control {
  padding-right: 30px
}

.input_size_m .input__control {
  line-height: 32px
}

.input_size_m .input__control:-webkit-autofill {
  height: 32px;
  line-height: 32px
}

.radiobox {
  display: inline-block;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0)
}

.radiobox__radio_disabled_yes {
  pointer-events: none
}

.radiobox__control, .radiobox__radio {
  cursor: pointer
}

.radiobox__radio_disabled_yes, .radiobox__radio_disabled_yes .radiobox__control {
  cursor: default
}

.radiobox__radio {
  position: relative;
  touch-action: manipulation
}

.radiobox__box {
  position: relative;
  display: inline-block
}

.radiobox__control {
  position: absolute;
  opacity: 0
}

.radio-button, .radio-button__radio {
  display: inline-block;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none
}

.radio-button {
  white-space: nowrap;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
  font-family: inherit
}

.radio-button__radio {
  position: relative;
  z-index: 2;
  margin: 0 -1px 0 0;
  text-align: center;
  outline: 0;
  touch-action: manipulation
}

.radio-button__radio:after, .radio-button__radio:before {
  position: absolute;
  z-index: -1;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  content: ''
}

.radio-button__radio:after {
  z-index: -2;
  top: 1px;
  right: 1px;
  bottom: 1px;
  left: 1px
}

.radio-button__radio_side_left, .radio-button__radio_side_left:before {
  border-top-left-radius: 3px;
  border-bottom-left-radius: 3px
}

.radio-button__radio_side_right {
  margin-right: 0
}

.radio-button__radio_side_right, .radio-button__radio_side_right:before {
  border-top-right-radius: 3px;
  border-bottom-right-radius: 3px
}

.radio-button__radio_side_left:after {
  border-top-left-radius: 2px;
  border-bottom-left-radius: 2px
}

.radio-button__radio_side_right:after {
  right: 1px;
  border-top-right-radius: 2px;
  border-bottom-right-radius: 2px
}

.radio-button__radio_checked_yes:before {
  right: 0
}

.radio-button__radio_checked_yes + .radio-button__radio:before {
  left: 1px
}

.radio-button__radio_disabled_yes {
  pointer-events: none
}

.radio-button__radio {
  cursor: pointer
}

.radio-button__radio_disabled_yes {
  cursor: default
}

.radio-button__radio_checked_yes + .radio-button__radio::before {
  left: 1px
}

.radio-button__control {
  position: absolute;
  opacity: 0;
  cursor: pointer
}

.radio-button__text {
  position: relative;
  z-index: 1;
  padding: 0 1em;
  pointer-events: none
}

.radio-button__radio_side_both {
  border-radius: 3px
}

.radio-button__radio_side_both:before {
  right: 0;
  border-radius: 3px
}

.radio-button__radio_side_both:after {
  border-radius: 2px
}

.radio-button_size_s {
  font-size: 13px;
  line-height: 28px
}

.radio-button.radio-button_size_s {
  height: 24px;
  font-size: 11px;
  line-height: 24px
}

.radio-button.radio-button_size_s .radio-button__shadow::after {
  top: 2px;
  right: 2px;
  bottom: 2px;
  left: 2px
}

.radio-button_theme_default.radio-button_count_1 .radio-button__radio {
  width: 100%
}

.radio-button_theme_default.radio-button_count_2 .radio-button__radio {
  width: 50%
}

.radio-button_theme_default.radio-button_count_3 .radio-button__radio {
  width: 33.333333%
}

.radio-button_theme_default.radio-button_count_4 .radio-button__radio {
  width: 25%
}

.radio-button_theme_default.radio-button_count_5 .radio-button__radio {
  width: 20%
}

.radio-button_theme_default.radio-button_count_6 .radio-button__radio {
  width: 16.666666666666668%
}

.radio-button_theme_default {
  position: relative;
  box-sizing: border-box;
  width: 100%;
  cursor: pointer;
  border-radius: 4px;
  background: #e6e6e6
}

.radio-button_theme_default .radio-button__radio {
  display: table-cell;
  text-align: center;
  color: gray
}

.radio-button_theme_default .radio-button__radio_checked_yes, .radio-button_theme_default .radio-button__radio_pressed_yes {
  color: #000
}

.radio-button_theme_default .radio-button__shadow {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  box-sizing: border-box;
  border: solid 3px rgba(255, 255, 255, 0);
  border-radius: 5px;
  background: #fff;
  background-clip: content-box;
  transition: transform .2s;
  transition: transform .2s, -webkit-transform .2s
}

.radio-button_theme_default .radio-button__radio > .radio-button__shadow {
  right: 0;
  left: 0
}

.radio-button_theme_default .radio-button__content {
  display: inline-table;
  width: 100%
}

.clearfix:after {
  display: block;
  clear: both;
  height: 0;
  content: ''
}

.organic {
  position: relative
}

.organic__last-seen_middledot {
  float: left;
  margin-right: 4px
}

.organic__subtitle_overflow_yes {
  overflow: hidden;
  height: 18px
}

.direct-label {
  display: inline-block;
  -webkit-align-self: center;
  align-self: center;
  width: 59px;
  min-width: 59px;
  height: 15px;
  margin-left: 12px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  vertical-align: middle;
  background-repeat: no-repeat;
  background-size: 59px 15px
}

.direct-label_align_left {
  margin-right: 12px;
  margin-left: 0
}

.composite__item_fullwidth_yes {
  margin-right: -30px;
  margin-left: -30px
}

.composite__item.serp-item {
  width: auto;
  margin: 0
}

.composite__item_separated_yes::before {
  margin: 16px 0
}

.composite__item:last-child.composite__item_clear_both, .composite__item:last-child.composite__item_clear_bottom {
  margin-bottom: -26px
}

.composite__item:last-child.composite__item_clear_both .button2_width_max, .composite__item:last-child.composite__item_clear_bottom .button2_width_max {
  vertical-align: top
}

.composite_gap_m > .composite__item, .composite_gap_m > .composite__item + .fold__show-more {
  margin-top: 26px
}

.composite_gap_xm > .composite__item, .composite_gap_xm > .composite__item + .fold__show-more {
  margin-top: 16px
}

.composite_gap_s > .composite__item, .composite_gap_s > .composite__item + .fold__show-more {
  margin-top: 10px
}

.composite_gap_xs > .composite__item, .composite_gap_xs > .composite__item + .fold__show-more {
  margin-top: 6px
}

.composite_gap_xxs > .composite__item, .composite_gap_xxs > .composite__item + .fold__show-more {
  margin-top: 4px
}

.composite_gap_xxxs > .composite__item, .composite_gap_xxxs > .composite__item + .fold__show-more {
  margin-top: 2px
}

.composite__item:first-of-type {
  margin-top: 0;
  padding-top: 0
}

.composite__item_padding-top_s {
  padding-top: 10px
}

.composite_top-margin_-xs {
  margin-top: -8px
}

.composite_top-margin_s {
  margin-top: 12px
}

.composite_top-margin_xm {
  margin-top: 16px
}

.composite_top-margin_m {
  margin-top: 20px
}

.composite_bottom-margin_-xxs {
  margin-bottom: -4px
}

.composite_bottom-margin_s {
  margin-bottom: 12px
}

.composite_bottom-margin_m {
  margin-bottom: 20px
}

.composite_bottom-margin_none {
  margin-bottom: 0
}

.composite.composite_gap_m > .composite__item_clear_both, .composite.composite_gap_m > .composite__item_clear_bottom {
  margin-bottom: -26px
}

.composite.composite_gap_s > .composite__item_clear_both, .composite.composite_gap_s > .composite__item_clear_bottom {
  margin-bottom: -10px
}

.composite.composite_gap_m > .composite__item_clear_both, .composite.composite_gap_m > .composite__item_clear_top, .composite.composite_gap_s > .composite__item_clear_both, .composite.composite_gap_s > .composite__item_clear_top, .composite.composite_gap_xs > .composite__item_clear_both, .composite.composite_gap_xs > .composite__item_clear_top {
  margin-top: 0;
  padding-top: 0
}

.composite.composite_gap_xxs > .composite__item_clear_top {
  margin-top: 4px
}

.composite.composite_gap_xxs > .composite__item_clear_both, .composite.composite_gap_xxxs > .composite__item_clear_both {
  margin-top: 0;
  padding-top: 0
}

.serp-list > .serp-item > .composite {
  margin-bottom: 26px
}

.serp-list > .serp-item > .composite_bottom-margin_none, .serp-list > .serp-item > .fold .fold__body > .composite {
  margin-bottom: 0
}

.composite_gap_none > .composite__item {
  margin-top: 0;
  margin-bottom: 0
}

.composite_padding_m {
  padding: 20px 30px
}

.composite__item_relative_yes {
  position: relative
}

.composite__item_separated_yes::before {
  display: block;
  content: '';
  border-bottom: 1px solid rgba(0, 0, 0, .1)
}

.composite .composite__item_bottom-margin_m[class] {
  margin-bottom: 20px
}

.composite .composite__item_top-margin_m[class] {
  margin-top: 20px
}</style>