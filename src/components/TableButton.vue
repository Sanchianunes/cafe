<template>
  <div>
    <div class="toggle-button-cover">
      <div class="button-cover">
        <div id="button-1" class="button r">
          <input type="checkbox" class="checkbox" />
          <div class="knobs"></div>
          <div class="layer"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss">
.toggle-button-cover {
  display: table-cell;
  position: relative;
  width: 200px;
  height: 140px;
  box-sizing: border-box;

  .button-cover {
    height: 100px;
    margin: 20px;
    background-color: #fff;
    box-shadow: 0 10px 20px -8px #c5d6d6;
    border-radius: 4px;

    &:before {
      counter-increment: button-counter;
      content: counter(button-counter);
      position: absolute;
      right: 0;
      bottom: 0;
      color: black;
      font-size: 18px;
      line-height: 1;
      padding: 5px;
    }

    /* Button 1 */
    #button-1 .knobs:before {
      content: 'YES';
      position: absolute;
      top: 4px;
      left: 4px;
      width: 20px;
      height: 10px;
      color: #fff;
      font-size: 10px;
      font-weight: bold;
      text-align: center;
      line-height: 1;
      padding: 9px 4px;
      background-color: #03a9f4;
      border-radius: 50%;
      transition: 0.3s cubic-bezier(0.18, 0.89, 0.35, 1.15) all;
    }

    #button-1 .checkbox:checked + .knobs:before {
      content: 'NO';
      left: 42px;
      background-color: #f44336;
    }

    #button-1 .checkbox:checked ~ .layer {
      background-color: #fcebeb;
    }

    #button-1 .knobs,
    #button-1 .knobs:before,
    #button-1 .layer {
      transition: 0.3s ease all;
    }
  }
}
</style>
