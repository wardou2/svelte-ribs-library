<script lang="ts">
    import { createEventDispatcher } from 'svelte';

    export let primary = false;
    export let size = 'medium';
    export let label = '';

    const dispatch = createEventDispatcher();
    function onClick(event) {
        dispatch('click', event);
    }
</script>

<button
    type="button"
    class={['btn', `btn-${primary ? 'primary' : 'secondary'}`].join(' ')}
    on:click={onClick}
>
    {label}
</button>

<style>
    .srl-button {
        font-family: 'Nunito Sans', 'Helvetica Neue', Helvetica, Arial, sans-serif;
        font-weight: 700;
        border: 0;
        border-radius: 3px;
        cursor: pointer;
        display: inline-block;
        line-height: 1;
    }
    .srl-button--primary {
        color: #1b116e;
        background-color: #6bedb5;
    }
    .srl-button--secondary {
        color: #ffffff;
        background-color: #1b116e;
        box-shadow: rgba(0, 0, 0, 0.15) 0px 0px 0px 1px inset;
    }
    .srl-button--small {
        font-size: 12px;
        padding: 10px 16px;
    }
    .srl-button--medium {
        font-size: 14px;
        padding: 11px 20px;
    }
    .srl-button--large {
        font-size: 16px;
        padding: 12px 24px;
    }

    .srl-button--primary :hover {
        color: #1b116e;
        background-color: #55bd90;
    }

    .srl-button--primary :active {
        color: #1b116e;
        background-color: #55bd90;
        border: solid 2px #1b116e;
    }

    .srl-button--primary :disabled {
        color: #1b116e;
        opacity: 0.5;
        background-color: #6bedb5;
    }

    .srl-button--secondary :hover {
        color: #1b116e;
        background-color: #55bd90;
    }

    .srl-button--secondary :active {
        color: #1b116e;
        background-color: #6bedb5;
        border: solid 2px #1b116e;
    }

    .srl-button--secondary :disabled {
        color: #ffffff;
        opacity: 0.5;
        background-color: #1b116e;
    }
</style>
