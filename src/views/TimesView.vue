<script>
import { v4 as uuidv4 } from "uuid";
export default {
  data() {
    return {
      times: [
        { id: "4dfadc62-3011-48a9-a384-53cbc062b0b2", nome: "Time 1" },
        { id: "6fe0c8e2-619b-4c46-b92b-e1ca7a3b970c", nome: "TIme 2" },
        { id: "9e3a44e1-bceb-4786-a1fd-38c5a76a7745", nome: "Time 3" },
      ],
      novo_time: "",
    };
  },
  methods: {
    salvar() {
      if (this.novo_time !== "") {
        const novo_id = uuidv4();
        this.times.push({
          id: novo_id,
          nome: this.novo_time,
        });
      }
    },
    excluir(time) {
      const indice = this.times.indexOf(time);
      this.times.splice(indice, 1);
    },
  },
};
</script>

<template>
  <div class="container">
    <div class="title">
      <h2>Gerenciamento de Times</h2>
    </div>
    <div class="form-input">
      <input type="text" v-model="novo_time" @keydown.enter="salvar" />
      <button @click="salvar">Salvar</button>
    </div>
    <div class="list-times">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Nome</th>
            <th>Ações</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="time in times" :key="time.id">
            <td>{{ time.id }}</td>
            <td>{{ time.nome }}</td>
            <td>
              <button>Editar</button
              ><button @click="excluir(time)">Excluir</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
  <RouterView />
</template>

<style>
.title {
  text-align: center;
  margin: 2rem 0;
}

.form-input {
  display: flex;
  justify-content: center;
  margin: 2rem 0;
}

.form-input input {
  width: 50%;
  padding: 0.5rem;
  border: 2px solid #000000;
  border-radius: 5px;
}

.form-input button {
  padding: 0.5rem;
  border: 2px solid #000000;
  border-radius: 5px;
  color: #454663;
  font-weight: bold;
  margin-left: 1%;
}

.list-times {
  display: flex;
  justify-content: center;
}

table {
  width: 80%;
  border-collapse: collapse;
  margin: 0 auto;
  border: 1px solid #101010;
  font-size: 1.1rem;
  text-align: center;
}

table thead {
  background-color: #3a3535;
  color: #ffffff;
}

table thead th {
  font-weight: bolder;
}

table tbody tr:nth-child(odd) {
  background-color: #9c9c9c;
}
</style>
