<script>
    import { Meta, Template, Story } from '@storybook/addon-svelte-csf';
    import Button from './Button.svelte';
</script>

<Meta
    title="RIBS Component Library/Button"
    component={Button}
    argTypes={{
        label: { control: 'text' },
        primary: { control: 'boolean' },
        backgroundColor: { control: 'color' },
        size: {
            control: { type: 'select', options: ['small', 'medium', 'large'] }
        },
        onClick: { action: 'onClick' }
    }}
/>

<Template let:args>
    <Button {...args} on:click={args.onClick} />
</Template>

<Story
    name="Primary"
    args={{
        primary: true,
        label: 'Button'
    }}
/>

<Story
    name="Secondary"
    args={{
        label: 'Button'
    }}
/>
