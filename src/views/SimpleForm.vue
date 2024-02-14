<template>
  <div>
    <h1>Create an event</h1>
    <form>

      <!-- <label>Select a category</label>
      <select v-model="event.category">
        <option
          v-for="option in categories"
          :value="option"
          :key="option"
          :selected="option === event.category"
        >{{ option }}</option>
      </select> -->
      <BaseSelect :options="categories"
      v-model="event.category"
      slabel="Select a aaacategory"
      />

      <h3>Name & describe your event</h3>

      <BaseInput
        v-model="event.title"
        label="Title"
        type="text"/>

      <BaseInput
      v-model="event.description"
      label="Description"
      type="text"/>

      <h3>Where is your event?</h3>
      <BaseInput
      v-model="event.location"
      label="Location"
      type="text"/>

      <h3>Are pets allowed?</h3>
      <div>
        <BaseRadio
          v-model="event.pets"
          :value="1"
          label="Yes"
          name="pets"
        />
      </div>

      <div>
        <BaseRadio
          v-model="event.pets"
          :value="0"
          label="No"
          name="pets"
        />
      </div>

      <h3>Extras</h3>
      <div>
        <BaseCheckbox
          v-model="event.extras.catering"
          label="Catering"
        />
      </div>

      <div>
        <BaseCheckbox
          v-model="event.extras.music"
          label="Live music"
        />
      </div>

      <button type="submit">Submit</button>
    </form>

    <pre>{{ event }}</pre>
  </div>
</template>

<script>

export default {
  data () {
    return {
      // Aa: 'ssssss',
      categories: [
        'sustainability',
        'nature',
        'animal welfare',
        'housing',
        'education',
        'food',
        'community'
      ],
      event: {
        category: '',
        title: '',
        description: '',
        location: '',
        pets: 1,
        extras: {
          catering: false,
          music: false
        }
      }
    }
  }
}
</script>
