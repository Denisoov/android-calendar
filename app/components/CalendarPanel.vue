<template>
    <FlexboxLayout height="50" class="calendar-panel">
    <Button 
        text="<" 
        class="calendar-panel__prev"
        width="30"
        height="30"
    />
    <Label class="calendar-panel__mounth" :text="monthName" width="120" height="30"/>
    <Button 
        text=">"
        class="calendar-panel__next"
        width="30"
        height="30"
    />
    </FlexboxLayout>
</template>

<script>

export default {
    props: {
        monthName: {
            type: String
        }
    }
}
</script>