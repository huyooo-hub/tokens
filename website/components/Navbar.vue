<script setup lang="ts">
import type { PropType } from 'vue';
import type { DesignToken } from 'pinceau';

defineProps({
  hoveredToken: {
    type: Object as PropType<DesignToken | undefined>,
    required: false,
  },
  clipboardState: {
    type: String,
    required: false,
  },
  type: {
    type: String as PropType<'variable' | 'token'>,
    required: false,
  },
});
</script>

<template>
  <header>
    <h1>
      <IconNuxt class="icon" />
      <span>@huyooo-hub/tokens</span>
    </h1>
    <div>
      <TokenBadge
        :type="type"
        :clipboard-state="clipboardState"
        :token="hoveredToken"
      />
      <ThemeSelect />
      <NuxtLink to="https://github.com/nuxt-themes/tokens" target="_blank">
        <Icon name="fa-brands:github" />
      </NuxtLink>
    </div>
  </header>
</template>

<style scoped lang="ts">
css({
  header: {
    overflow: 'hidden',
    height: '{huyooo.size.64}',
    backdropFilter: 'saturate(180%) blur(20px)',
    width: '100%',
    padding: '{huyooo.space.4} {huyooo.space.8}',
    position: 'sticky',
    top: '{huyooo.space.0}',
    display: 'flex',
    justifyContent: 'space-between',
    alignItems: 'center',
    '@dark': {
      backgroundColor: 'rgba({huyooo.color.black}, 0.4)',
    },
    a: {
      lineHeight: '0'
    },
    zIndex: '50',
    h1: {
      display: 'flex',
      alignItems: 'center',
      gap: '{huyooo.space.2}',
      fontSize: '{fontSize.sm}',
      fontWeight: '{fontWeight.black}',
      '@xl': {
        fontSize: '{fontSize.xl}',
      },
      '.icon': {
        width: '{huyooo.size.32}'
      },
      span: {
        display: 'none'
      },
      '@xs': {
        span: {
          display: 'inline',
        }
      },
    },
    '& > div': {
      display: 'flex',
      justifyContent: 'space-between',
      alignItems: 'center',
      '& > * + *': {
        marginLeft: '{huyooo.space.4}'
      },
      ':deep(.icon)': {
        height: '{huyooo.size.16}',
        width: '{huyooo.size.16}'
      },
      '@xl': {
        ':deep(.icon)': {
          height: '{huyooo.size.24}',
          width: '{huyooo.size.24}'
        }
      }
    }
  }
})
</style>
