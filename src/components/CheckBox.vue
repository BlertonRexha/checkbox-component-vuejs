<template>
    <label class="checkbox-item">
        <input type="checkbox" :checked="value" @change="$emit('input', $event.target.checked)" class="checkbox-input">
        <span class="check-span">
            <slot></slot>
        </span>
    </label>
</template>
<script>
export default {
    name: "CheckBox",
    props: ['value']
}
</script>
<style scoped>
.checkbox-item {
    display: block;
    position: relative;
    padding-left: 5px;
    margin: auto;
    cursor: pointer;
    font-size: 22px;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
}

.checkbox-item input {
    position: absolute;
    opacity: 0;
    cursor: pointer;
    height: 0;
    width: 0;
}

.check-span {
    position: absolute;
    top: 0;
    left: 0;
    height: 13px;
    width: 14px;
    border-radius: 3px;
}

.checkbox-item:hover input~.check-span {
    background-color: #fdfdfd;
    border: 1px solid #2196F3;
}

.checkbox-item input~.check-span {
    transition: 0.3s all;
    border: 1px solid #d4d4d4;
}

.checkbox-item input:checked~.check-span {
    background-color: #2196F3;
    border: 1px solid #2196F3;

}

.check-span:after {
    content: "";
    position: absolute;
    display: none;
}

.checkbox-item input:checked~.check-span:after {
    display: block;
}

.checkbox-item .check-span:after {
    left: 5px;
    top: 0px;
    width: 3px;
    height: 9px;
    border: solid white;
    border-width: 0px 1px 1px 0;
    -webkit-transform: rotate(45deg);
    transform: rotate(45deg);
}
</style>
