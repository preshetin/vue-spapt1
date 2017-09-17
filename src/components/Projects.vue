<template>

  <!-- Hero content: will be in the middle -->

    <div class="container is-default" style="margin: 0 40px">
      <br>
      <h1 class="title">
        Проекты
        <a class="button is-large" @click="showModal()">
          <span class="icon is-medium">
            <i class="fa fa-plus"></i>
          </span>
          <span>Добавить</span>
        </a>
      </h1>

      <ul>
        <div class="box" v-for="project in projects">
          <article class="media">
            <div class="media-left">
              <figure class="image is-64x64">
                <img src="http://bulma.io/images/placeholders/128x128.png" alt="Image">
              </figure>
            </div>
            <div class="media-content">
              <div class="content">
                <p>
                  <strong>{{ project.title }}</strong> <small>@velcom</small> <small>31m</small>
                  <br>
                  {{ project.description}}
                </p>
              </div>
              <nav class="level is-mobile">
                <div class="level-right">
                  <div class="level-item">
                    {{ project.bonus}}&nbsp;<span class="icon is-small"><i class="fa fa-tree"></i></span>
                  </div>
                  &nbsp;

                  <a class="level-item" v-if="!project.isApplied">
                    <a class="button is-success" @click="apply(project.id)">Откликнуться</a>&nbsp;
                  </a>
                  <a class="level-item" v-else>
                    <a class="button is-dark is-outlined" disabled><i class="fa fa-check" aria-hidden="true"></i>&nbsp;Вы откликнулись</a>&nbsp;
                  </a>
                </div>
              </nav>
            </div>
          </article>
        </div>


        <div class="modal is-active" v-if="isModalShow">
          <div class="modal-background"></div>
          <div class="modal-card">
            <header class="modal-card-head">
              <p class="modal-card-title">Добавить проект</p>
              <button class="delete" aria-label="close" @click="closeModal()"></button>
            </header>
            <section class="modal-card-body">
              <div class="field is-horizontal">
                <div class="field-label is-normal">
                  <label class="label">Название</label>
                </div>
                <div class="field-body">
                  <div class="field">
                    <p class="control is-expanded">
                      <input class="input" type="text" placeholder="Name" v-model="form.title">
                    </p>
                  </div>
                </div>
              </div>


              <div class="field is-horizontal">
                <div class="field-label is-normal">
                  <label class="label">Бонус</label>
                </div>
                <div class="field-body">
                  <div class="field">
                    <p class="control is-expanded has-icons-left">
                      <input class="input" type="text" placeholder="Price" v-model="form.price">
                      <span class="icon is-small is-left">
                        <i class="fa fa-tree"></i>
                      </span>
                    </p>
                  </div>
                </div>
              </div>


              <div class="field is-horizontal">
                <div class="field-label is-normal">
                  <label class="label">Описание</label>
                </div>
                <div class="field-body">
                  <div class="field">
                    <div class="control">
                      <textarea class="textarea" placeholder="Explain how we can help you" v-model="form.description"></textarea>
                    </div>
                  </div>
                </div>
              </div>

            </section>
            <footer class="modal-card-foot">
              <button class="button is-success" @click="store()">Добавить проект</button>
              <button class="button" @click="closeModal()">Отмена</button>
            </footer>
          </div>
        </div>

      </ul>
    </div>


</template>

<script>
export default {
  name: 'projects',
  mounted() {
    this.getProjects();
  },

  methods: {
    showModal() {
      this.isModalShow = true;
    },
    closeModal() {
      this.isModalShow = false;
    },
    getProjects() {
      axios.get("https://social-point.herokuapp.com/projects")
        .then(response => {this.projects = response.data});
    },
    store() {
      console.log('storing...');
      axios.post("https://social-point.herokuapp.com/projects", this.form,{
          headers: {
            'Accept': 'application/json',
            'Content-Type': "application/json" }
          })
            .then(response => {
                this.getProjects();
                this.form.title = '';
                this.form.description = '';
                this.form.price = null,
                this.form.bonus = '',
                this.isModalShow = false;
            });
    },
    apply(project_id) {
      var project = this.projects.filter(function(project){ return project.id == project_id;} )[0];
      console.log(project);
      project.isApplied = true;
      this.projects.splice(project_id - 1, 1, project);
      console.log('applied for project id:' + project_id);
    }
  },

  data() {
    return {
      isModalShow: false,
      projects: [],
      form: {
        title: "",
        description: "",
        organizationId: "59bdd6cf1ae4940004dc925f",
        price: 33,
        bonus: 'some bonus'
      }
    }
  }
}
</script>
<!-- styling for the component -->
<style>
#projects {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
