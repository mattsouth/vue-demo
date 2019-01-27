<template>
  <main role="main">
    <div class="container">
      <div class="row">
        <div class="col-sm">
          <h1>Reactive editor</h1>
        </div>
        <div class="col-sm">
          <button id="clear" type="button" class="mt-3 btn btn-sm btn-outline-primary float-sm-right" @click="clearText">Clear</button>
        </div>
      </div>
      <div class="row">
        <div class="col-sm">
          <div class="form-group">
            <simple-editor id="left" rows="5" :text="text" @keyup="updateText"></simple-editor>
          </div>
        </div>
        <div class="col-sm">
          <div class="form-group">
            <simple-editor id="right" rows="5" :text="text" @keyup="updateText"></simple-editor>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-sm">
          <pre>{{text}}</pre>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import { ReactiveVar } from 'meteor/reactive-var';
import SimpleEditor from '../imports/components/SimpleEditor.vue';

Text = new ReactiveVar('Some test text');

export default {
  components: {
    'simple-editor': SimpleEditor
  },
  methods: {
    updateText(e) {
      Text.set(e.target.value);
    },
    clearText() {
      Text.set("");
    }
  },
  meteor: {
    text() {
      return Text.get();
    }
  }
}
</script>
