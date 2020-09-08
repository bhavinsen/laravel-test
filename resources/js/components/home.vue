<template>
  <div class="container">
    <div class="container">
      <b-card no-body>
        <b-tabs v-model="tabIndex" card>
          <b-tab title="Draft Countdown">
            <div class="managecard">
              <center>
                <h4 class='grey'>This Draft Starts:</h4>
                <h4 class="bold">Mon, Nov 6 at 6:55 PM</h4>
                <count-down
                  starttime="Sep 8, 2020 12:04:25"
                  endtime="Sep 9, 2020 16:37:25"
                  trans='{
                "day":"Day",
                "hours":"Hours",
                "minutes":"Minuts",
                "seconds":"Seconds",
                "expired":"Event has been expired.",
                "running":"Till the end of event.",
                "upcoming":"Till start of event.",
                "status": {
                    "expired":"Expired",
                    "running":"Running",
                    "upcoming":"Future"
                  }}'
                ></count-down>
              </center>
            </div>
            <br/>
             <div class="managecard">
               <center>
                <h4 class="bold">Pre-Draft Player Ranking!</h4>
                 <h4 class='grey' >Create your draft strategy and be ready.</h4>
                 <button class='btn btn-default draft'>Pre-Draft</button>
                 </center>
             </div>
          </b-tab>
          <b-tab title="Autopick Strategy">Autopick Strategy</b-tab>
          <b-tab title="League Rules">League Rules</b-tab>
        </b-tabs>
      </b-card>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Btable from './Btable';

export default {
  components: {
    'count-down': Btable,
  },
  props: {
    msg: String,
  },
  data() {
    return {
      tabIndex: 0,
    };
  },
  methods: {
    linkClass(idx) {
      if (this.tabIndex === idx) {
        return ["bg-primary", "text-light"];
      } else {
        return ["bg-light", "text-info"];
      }
    },
  },
};
</script>
