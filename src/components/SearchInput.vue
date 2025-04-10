<script setup lang="ts">
import { cn } from '@/lib/utils'
import { Combobox, ComboboxAnchor, ComboboxEmpty, ComboboxGroup, ComboboxInput, ComboboxItem, ComboboxItemIndicator, ComboboxList } from '@/components/ui/combobox'
import { Check, Search } from 'lucide-vue-next'

defineProps<{ movies: Array<object> }>()

</script>

<template>
    <div>
        <p class="font-bold text-xl mb-5">Search by movie name:</p>
        <Combobox class="w-md" by="label">
            <ComboboxAnchor class="w-full">
                <div class="relative w-full items-center">
                    <ComboboxInput class="pl-9" :display-value="(val) => val?.label ?? ''" />
                    <span class="absolute start-0 inset-y-0 flex items-center justify-center px-3">
                        <Search class="size-4 text-muted-foreground" />
                    </span>
                </div>
            </ComboboxAnchor>

            <ComboboxList>
                <ComboboxEmpty>
                    No movies found.
                </ComboboxEmpty>

                <ComboboxGroup>
                    <ComboboxItem v-for="movie in movies" :key="movie.value" :value="movie">
                        {{ movie.label }}

                        <ComboboxItemIndicator>
                            <Check :class="cn('ml-auto h-4 w-4')" />
                        </ComboboxItemIndicator>
                    </ComboboxItem>
                </ComboboxGroup>
            </ComboboxList>
        </Combobox>
    </div>
</template>