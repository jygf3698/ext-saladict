<template>
  <div class="opt-item"><!-- 自动发音 -->
    <div class="opt-item__header">
      <strong>{{ $i18n('opt_autopron_title') }}</strong>
    </div>
    <div class="opt-item__body">
       <div class="select-box-container">
          <label class="select-box">
            <span class="select-label">{{ $i18n('opt_autopron_cn') }}</span>
            <select class="form-control" v-model="autopron.cn.dict">
              <option value="">{{ $i18n('opt_none') }}</option>
              <option v-for="id in autopron.cn.list" :value="id">{{ $i18n('dict_' + id) }}</option>
            </select>
          </label>
          <label class="select-box">
            <span class="select-label">{{ $i18n('opt_autopron_en') }}</span>
            <select class="form-control" v-model="autopron.en.dict">
              <option value="">{{ $i18n('opt_none') }}</option>
              <option v-for="id in autopron.en.list" :value="id">{{ $i18n('dict_' + id) }}</option>
            </select>
          </label>
          <span :style="{transition: 'opacity 0.4s', opacity: autopron.en.dict ? '1' : '0'}">
            <label class="radio-inline">
              <input type="radio" value="uk" v-model="autopron.en.accent"> {{ $i18n('opt_autopron_uk') }}
            </label>
            <label class="radio-inline">
              <input type="radio" value="us" v-model="autopron.en.accent"> {{ $i18n('opt_autopron_us') }}
            </label>
          </span>
       </div>
    </div>
    <div class="opt-item__description-wrap">
      <p class="opt-item__description" v-html="$i18n('opt_autopron_description')"></p>
    </div>
  </div><!-- 自动发音 -->
</template>

<script>
export default {
  store: {
    autopron: 'config.autopron',
  }
}
</script>
