<template>

  <div id="Pasadia" class="Pasadia">
    <div class="container_pasadia">
      <h2>Comprar Pasadia</h2>

      <form v-on:submit.prevent="processPasadia">
        <input
          type="text"
          v-model="Pasadia"
          placeholder="Pasadia"
        />
        <button type="submit">Comprar Pasadia</button>
      </form>
    </div>
  </div>

</template>


<script>
/*import gql from "graphql-tag";

export default {
  name: "Pasadia",

  data: function() {
    return {
      createPasadia: {
        //idhotel"Origin: localStorage.getItem("idhotel")
      },
    };
  },

  methods: {
    processPasadia: async function() {
      
      if (localStorage.getItem("token_access")  === null ||
          localStorage.getItem("token_refresh") === null ) {
        this.$emit("logOut");
        return;
      }

      localStorage.setItem("token_access", "");

      await this.$apollo
        .mutate({
          mutation: gql`
            mutation ($refresh: String!) {
              refreshToken(refresh: $refresh) {
                access
              }
            }
          `,
          variables: {
            refresh: localStorage.getItem("token_refresh"),
          },
        })
        .then((result) => {
          localStorage.setItem("token_access", result.data.refreshToken.access);
        })
        .catch((error) => {
          this.$emit("logOut");
          return;
        });
      
      await this.$apollo
        .mutate({
          mutation: gql`
            mutation($pasadia: PasadiaInput!) {
              createPasadia(pasadia: $pasadia) {
                idpas
                idpasadia
                nombreHotel
                ciudad
                fechaIn
                valorPasadia
              }
            }
          `,
          variables: {
            pasadia: this.createPasadia,
          },
        })
        .then((result) => {
          alert("Pasadia adquirido de Manera Correcta, Revise Historial");
        })
        .catch((error) => {
          alert("No se encontró pasadia o no está disponible");
        });
    },
  },
}; */
</script>


<style>

.pasadia {
  margin: 0;
  padding: 0%;
  height: 100%;
  width: 100%;

  display: flex;
  justify-content: center;
  align-items: center;
}

.container_pasadia {
  border: 3px solid #283747;
  border-radius: 10px;
  width: 25%;
  height: 60%;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.pasadia h2 {
  color: #283747;
}

.pasadia form {
  width: 50%;
}

.pasadia input {
  height: 40px;
  width: 100%;

  box-sizing: border-box;
  padding: 10px 20px;
  margin: 5px 0;

  border: 1px solid #283747;
}

.pasadia button {
  width: 100%;
  height: 40px;

  color: #e5e7e9;
  background: #283747;
  border: 1px solid #e5e7e9;

  border-radius: 5px;
  padding: 10px 25px;
  margin: 5px 0;
}

.pasadia button:hover {
  color: #e5e7e9;
  background: crimson;
  border: 1px solid #283747;
}

</style>
