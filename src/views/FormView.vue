<script setup lang="ts">
import { reactive } from 'vue'

interface FormulaireInscription {
    nom: string
    prenom: string
    email: string
    sexe: string
    institut: string
    adresse: string
    codePostal: string
    ville: string
}

function handleCancel(){
    Object.assign(form,{
        nom: '',
        prenom: '',
        email: '',
        sexe: '',
        institut: '',
        adresse: '',
        codePostal: '',
        ville: '',
    })
}

const form = reactive<FormulaireInscription>({
    nom: '',
    prenom: '',
    email: '',
    sexe: '',
    institut: '',
    adresse: '',
    codePostal: '',
    ville: '',
})

const handleSubmit = () => {
    console.log('Formulaire soumis :', form)
    alert('Formulaire soumis avec succès !')
}
</script>

<template>
    <div>
        <div>
        <h1>Formulaire d'inscription</h1>
        <form @submit.prevent="handleSubmit">
            <div>
            <label for="nom">Nom</label>
            <input v-model="form.nom" type="text" id="nom" required/>
            </div>
            <div>
            <label for="prenom">Prénom</label>
            <input v-model="form.prenom" type="text" id="prenom" required/>
            </div>
            <div>
            <label for="email">Email</label>
            <input v-model="form.email" type="email" id="email" required/>
            </div>
            <div>
            <span>Sexe</span>
            <div>
                <label>
                <input v-model="form.sexe" type="radio" value="Homme" />
                Homme
                </label>
                <label>
                <input v-model="form.sexe" type="radio" value="Femme" />
                Femme
                </label>
            </div>
            </div>
            <div>
            <label for="adresse">Adresse</label>
            <input v-model="form.adresse" type="text" id="adresse" required/>
            </div>
            <div>
            <label for="codePostal">Code postal</label>
            <input v-model="form.codePostal" type="text" id="codePostal" required/>
            </div>
            <div>
            <label for="ville">Ville</label>
            <input v-model="form.ville" type="text" id="ville" required/>
            </div>
            <div>
            <label for="institut">Nom de l'institut</label>
            <input v-model="form.institut" type="text" id="institut" required/>
            </div>
            <div>
            <button type="submit">Valider</button>
            </div>
            <div>
            <button type="button" @click="handleCancel">Annuler</button>
            </div>
        </form>
        </div>
    </div>
</template>

<style scoped>
input[type='text'],
input[type='email'],
select {
    width: 100%;
    padding: 12px 20px;
    margin: 8px 0;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
}

input[type='submit'] {
    width: 100%;
    background-color: #4caf50;
    color: white;
    padding: 14px 20px;
    margin: 8px 0;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

input[type='submit']:hover {
    background-color: #45a049;
}

div {
    border-radius: 5px;
    background-color: #f2f2f2;
    padding: 20px;
}
</style>