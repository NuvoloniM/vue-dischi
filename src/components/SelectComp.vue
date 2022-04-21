<template>
    <div>
        <select class="form-select" aria-label="Default select example">
            <option selected>Choose to filter by genre</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
        </select>
    </div>
</template>

<script>
export default {
    name: 'SelectComp'
}
</script>

<style lang="scss" scoped>
    div {
        padding: 10px;
    }
</style>