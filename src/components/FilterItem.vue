<template>
    <div class="container">
      <div class="row justify-content-md-center">
        <div class="col-md-6">
          <div class="card">
            <h4 class="card-header">
              Reversed
            </h4>
            <div class="card-body">
              <input class="form-control" v-model="reversed" placeholder="Reverse"/>
              <hr/>
              <input class="form-control" :value="reversed | reverse" placeholder="The Reversed Result" readonly/>
            </div>
          </div>
        </div>
        <div class="col-md-6">
          <div class="card">
            <h4 class="card-header">
              Wrapped
            </h4>
            <div class="card-body">
              <input class="form-control" v-model="wrapped" placeholder="Wrap"/>
              <hr/>
              <input class="form-control" :value="wrapped | wrap('(',')')" placeholder="The Wrapped Result" readonly/>
            </div>
          </div>
        </div>
        <div class="col-md-6">
          <div class="card">
            <h4 class="card-header">
              Combined
            </h4>
            <div class="card-body">
              <input class="form-control" v-model="combined" placeholder="Combine"/>
              <hr/>
              <input class="form-control" :value="combined | reverse | wrap('(',')')" placeholder="The Combined Result" readonly/>
            </div>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
    export default {
      name: "FilterItem",
      data: function () {
        return {
          reversed: null,
          wrapped: null,
          combined: null
        }
      },
      filters: {
        reverse: function (value) {
          if (! value) {
            return '';
          }
          return value.toString().split('').reverse().join('');
        },
        wrap: function (value, begin, end) {
          if (! value) {
            return '';
          }
          return begin + value.toString() + end;
        }
      }
    }
</script>

<style scoped>

</style>
