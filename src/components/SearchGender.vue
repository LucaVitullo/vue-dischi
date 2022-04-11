<template>
    <div>
        <div class="text-center p-2">
            <select class="p-1">
                <option value="">All</option>
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
            </select>
        </div>
    </div>
</template>

<script>
export default {
  name: "SearchGender",
  data() {
        return {
            SelectedGender: " ",
        };
     },
};
</script>

<style>
</style>