<!-- Copyright 2020 Google LLC

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    https://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License. -->

<script>
  import Logo from "../components/icons/Logo.svelte";
  import ButtonRoute from "../components/ButtonRoute.svelte";
  
  import frameworkInfo from "../utils/framework-info.json";
</script>

<style>
  .container {
    height: 100%;
    display: flex;
    align-items: center;
  }

  header {
    display: flex;
    padding-bottom: 4rem;
  }

  header h1 {
    font-weight: 600;
  }

  .frameworks {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-top: 5rem;
  }

  .divider {
    border: 2px solid #dddddd;
  }

  @media (max-width: 1240px) {
    header {
      flex-direction: column;
    }
    
    .title {
      text-align: center;
    }

    .frameworks {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      justify-items: center; 
      grid-row-gap: 3rem;
      grid-column-gap: 2rem;
    }

    .divider {
      width: 600px;
    }
  }

  @media (max-width: 715px) {
    header {
      padding: 0 2rem 2rem;
    }

    h1 {
      margin-bottom: 1rem;
    }

    h2 {
      font-size: 1.7rem;
    }

    .frameworks {
      grid-template-columns: repeat(2, 1fr);
      padding-top: 2rem;
    }

    .divider {
      width: 300px;
      margin: 1rem auto;
    }
  }
</style>

<div class="container">
  <div class="row">
    <header>
      <div class="title">
        <h1>
          Perf Track
        </h1>
        <h2>
          Tracking framework performance at scale
        </h2>
      </div>
    </header>
    <hr class ="divider"/>
    <div class="frameworks">
      {#each Object.keys(frameworkInfo) as framework}
        <ButtonRoute
          name={frameworkInfo[framework].name}
          route={frameworkInfo[framework].route}
          color={frameworkInfo[framework].color}
          img={frameworkInfo[framework].imgSrc} />
      {/each}
    </div>
  </div>
</div>
