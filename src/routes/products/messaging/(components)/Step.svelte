<script lang="ts">
    export let title: string;
    export let hideLine = false;
</script>

<div class="step" data-hideline={hideLine}>
    <div class="web-dot" />
    <h2 class="web-eyebrow web-u-color-text-primary step-title">{title}</h2>
    <div class="u-margin-block-start-32 step-content">
        <slot />
    </div>
</div>

<style lang="scss">
    .step {
        border-inline-start: 1px solid hsl(var(--web-color-offset));
        padding-inline-start: 2rem;
        padding-block-end: var(--padding-block-end);
        position: relative;
        @media screen and (max-width: 1024px) {
            padding: unset;
            border: none;
        }

        .web-dot {
            position: absolute;
            inset-inline-start: calc(calc(var(--p-dot-size) / 2) * -1);
            @media screen and (max-width: 1024px) {
                display: none;
            }
        }

        &-content {
            @media screen and (max-width: 1024px) {
                width: calc(100vw - 40px);
            }
        }
    }
    .step[data-hideline='true'] {
        border-inline-start: 1px solid transparent;
    }
</style>
