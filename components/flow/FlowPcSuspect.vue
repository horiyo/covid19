<template>
  <div :class="$style.FlowComponent">
    <div :class="[$style.SubtleBox, $style.Box1]">
      <div :class="$style.RowItems">
        <div :class="$style.RowItemsHeader">
          {{ $t('不安に思う方') }}
        </div>
      </div>
      <div :class="$style.RowItems">
        <div :class="$style.CheckBox">
          {{ $t('微熱') }}
        </div>
        <div :class="$style.CheckBox">
          {{ $t('軽い咳') }}
        </div>
        <div :class="$style.CheckBox">
          {{ $t('感染の不安') }}
        </div>
      </div>
    </div>

    <div :class="[$style.SubtleBox, $style.Box2, $style.Center]">
      <div :class="$style.LargerText">
        {{ $t('一般電話相談窓口（コールセンター）') }}
      </div>
      <div :class="$style.SmallerText">
        {{ $t('8時30分から21時（土日祝含む）') }}
      </div>

      <div :class="$style.Tel">
        <a :class="$style.TelLink" href="tel:0952257485">
          0952-25-7485 
        </a>
      </div>
    </div>
  </div>
</template>

<i18n src="./FlowPcSuspect.i18n.json"></i18n>

<style module lang="scss">
.FlowComponent {
  color: $gray-2;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.Tel {
  @include largerThan($medium) {
    font-size: larger;
  }
}
.TelLink {
  display: flex;
  align-items: center;
  font-weight: bold;
  &:link,
  &:visited,
  &:hover,
  &:active,
  &:focus {
    color: inherit;
    text-decoration: none;
  }
  &::before {
    content: '';
    display: inline-block;
    margin-right: 5px;
    width: 26px;
    height: 26px;
    background-image: url(/flow/phone-24px.svg);
    background-repeat: no-repeat;
    background-size: contain;
  }
}

.CheckBox {
  position: relative;
  border: 2px solid $green-1;
  border-radius: 4px;
  margin: 8px 0;
  padding: 10px;
  max-width: 200px;
  text-align: center;
  font-weight: bold;
  font-size: calc(0.875rem + ((1vw - 7.68px) * 0.8929));
  @include largerThan($large) {
    font-size: 20px;
  }

  &::after {
    position: absolute;
    left: -8px;
    top: -8px;
    width: 24px;
    height: 24px;
    background-image: url(/flow/check_circle-24px.svg);
    background-size: contain;
    content: '';
  }

  &::before {
    position: absolute;
    left: -4px;
    top: -4px;
    width: 20px;
    height: 20px;
    background-color: white;
    content: '';
  }
}

.SubtleBox {
  @include card-container();
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  padding: 0.5em;
}

.Box1 {
  position: relative;
  flex-grow: 0;
  flex-shrink: 0;
  width: 60%;
  flex-direction: row;
  &::after {
    content: '';
    position: absolute;
    bottom: 40%;
    right: -30px;
    z-index: 1;
    display: block;
    width: 46px;
    height: 46px;
    background: url('/flow/flow_arrow.svg') no-repeat;
  }
}

.Box2 {
  flex-grow: 0;
  flex-shrink: 0;
  width: 38%;
  flex-direction: column;
  justify-content: center;
  div {
    margin: 0.5em;
  }
}

.RowItems {
  flex-grow: 1;
  text-align: center;
  margin: 0 4px;
  @include largerThan($large) {
    margin: 0 2em;
  }
}

.RowItemsHeader {
  font-size: smaller;
  &::before {
    content: '';
    display: block;
    margin: auto;
    width: 45px;
    height: 45px;
    background-image: url(/flow/sentiment_very_dissatisfied-24px.svg);
    background-repeat: no-repeat;
    background-size: contain;
  }
}

.FlowArrow {
  position: absolute;
  margin: 0 -20px;
  z-index: 1;
}

.LargerText {
  font-size: larger;
  font-weight: bold;
}

.Center {
  text-align: center;
}

.SmallerText {
  font-size: smaller;
}
</style>
