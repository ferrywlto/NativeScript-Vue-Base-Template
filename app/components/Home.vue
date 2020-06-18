<template>
    <Page>
        <ActionBar>
            <Label text="Home"/>
        </ActionBar>
        <FlexboxLayout width="100%" height="50%" alignItem="center" >
            <FlexboxLayout width="100%" alignItems="center" justifyContent="center" flexDirection="column">
                <Label class="info">
                    <FormattedString>
                        <Span class="fas" text.decode="&#xf135;"/>
                        <Span :text="message"/>
                    </FormattedString>
                </Label>
                <Label class="info">
                    <FormattedString>
                        <Span :text="foobar"/>
                    </FormattedString>
                </Label>
            </FlexboxLayout>
        </FlexboxLayout>
    </Page>
</template>

<script>
  export default {
      created() {
          console.log(ENV_SECRET);
      },
      data () {
        return {
            foo: ENV_SECRET.FOO,
            bar: ENV_SECRET.BAR,
        }
      },
    computed: {
        foobar() {
            return `${this.foo} ${this.bar}`;
        },
        message() {
            return "Blank {N}-Vue app";
        }
    }
  };
</script>

<style scoped lang="scss">
    @import '~@nativescript/theme/scss/variables/blue';

    // Custom styles
    .fas {
        @include colorize($color: accent);
    }

    .info {
        font-size: 20;
        horizontal-align: center;
        vertical-align: center;
    }
</style>
