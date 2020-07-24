<template>
  <div class="home-page">
    <div class="content">
      

      <div class="tile is-ancestor mt-5">
        <div class="tile is-4 is-vertical is-parent">
          <div class="tile is-child box">
            <p class="title">Why</p>
            <p>The answer is simple: we want to make logging a simple, centralized and easy to monitor your application to help you develop simpler, more readable and <code>print()</code>-free programs.</p>
          </div>
          <div class="tile is-child box">
            <p class="title">Future</p>
            <p>Currently TentaLog is oriented mainly in Python, but we are open to discussions and PR to implement the system in other languages too. Here you can find all the versions of TentaLog: <a>TentaLog | Versions</a></p>
          </div>
        </div>
        <div class="tile is-parent">
          <div class="tile is-child box">
            <p class="title">How</p>
            <p>TentaLog is a logging library on top of the default logging library in Python.</p>
            <p>We managed to integrate a simplier configuration-flow to ensure a quick integration in every app. You can configure your logging with a YAML file. A simple and light weight logging configuration is provided by default. We brought in this library our logging best practices ready to use with the default configuration.</p>
            <p>
              The Tentacle is the single unit of TentaLog, managing a single logger. To start logging with tentacle you can follow the <a>quick-start guide on GitHub</a>.
              This code will use the tentalog default configuration, that contains the configuration of two logging handlers, one for the console and one for a time based file rotation of 15 days. If the "mylogger" logger is not found in configuration, the "root" logger will be used and a warning message will be showed. If the name of the logger is not specified, the "root" logger will be used. If you want to use a custom configuration you can just initialize your Tentacle in a similar way with a 
              YAML file.
            </p>
          </div>
        </div>
      </div>

    
      <div class="columns is-desktop">
        <div class="column">
          <section>
            <b-message title="An important message" type="is-warning" has-icon aria-close-label="Close message">
            Tentalog is currently in heavy development. You can expect a stable v2.0 release for Aug. 2021          
            </b-message>
          </section>
        </div>
        <div class="column">
          <b-notification type="is-info"
            has-icon
            aria-close-label="Close notification">
            Logging is a means of tracking events that happen when some software runs. The software’s developer adds logging calls to their code to indicate that certain events have occurred. An event is described by a descriptive message which can optionally contain variable data (i.e. data that is potentially different for each occurrence of the event). Events also have an importance which the developer ascribes to the event; the importance can also be called the level or severity.
          </b-notification> 
        </div>
      </div>
  

    
    </div> 
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  }
}
</script>

<style scoped>
  .home-page {
    padding: 25px;
  }
</style>
