<template>
  <!-- <section>
    <h1>キャラクターリスト</h1>
    <p>懸賞金の合計:{{ totalBounty }}</p>
    <OneCharacter2
      v-for="[id, character] in characterList"
      :key="id"
      :name="character.name"
      :id="id"
      :bounty="character.bounty"
      @incrementBounty="onIncrementBounty"
    />
  </section> -->
  <BaseSection />
  <TestComponent text="props" />
  <TestComponent />
</template>

<script setup lang="ts">
import type { Character } from "@/interfaces";
/**===================================================================================================================
 *
 ===================================================================================================================**/
//------------------------------------------------------------------------------------------------------------
// 引数
//------------------------------------------------------------------------------------------------------------
//------------------------------------------------------------------------------------------------------------
// 定数・変数（state）
//------------------------------------------------------------------------------------------------------------
// キャラクターリストデータ
useState<Map<number, Character>>(
  "characterList", //ステート名
  (): Map<number, Character> => {
    const characterListInit = new Map<number, Character>();
    characterListInit.set(1, { id: 1, name: "ルフィ", bounty: 100000000 });
    characterListInit.set(2, { id: 2, name: "ゾロ", bounty: 60000000 });
    return characterListInit;
  }
);
// キャラクターリストデータ
// const characterListInit = new Map<number, Character>();
// characterListInit.set(1, { id: 1, name: "ルフィ", bounty: 100000000 });
// characterListInit.set(2, { id: 2, name: "ゾロ", bounty: 60000000 });
// const characterList = ref(characterListInit);

// // キャラクターインターフェース
// interface Character {
//   id: number;
//   name: string;
//   bounty: number;
// }
// interfases.tsファイルへ

// const totalBounty = computed((): number => {
//   let total = 0;
//   for (const character of characterList.value.values()) {
//     total += character.bounty;
//   }
//   return total;
// });

// // 依頼より実行されるメソッド
// const onIncrementBounty = (id: number): void => {
//   // オブジェクト取得
//   const character = characterList.value.get(id);
//   // オブジェクトが存在するなら
//   if (character != undefined) {
//     // 懸賞金アップ
//     character.bounty += 1000;
//   }
// };

const gomgom = Math.round(Math.random() * 100);
const marchenGomgom = gomgom * 10;

//------------------------------------------------------------------------------------------------------------
// ライフサイクル
//------------------------------------------------------------------------------------------------------------
/*
onBeforeMount(() => {
  //記憶した位置、サイズでの復帰を可能にする
})

onMounted(() => {
  //window.addEventListener('resize', onGetPosition)
})

onBeforeUnmount(() => {
  //window.removeEventListener('resize', onGetPosition)
})
*/
//------------------------------------------------------------------------------------------------------------
//watch
//------------------------------------------------------------------------------------------------------------
/*
watch(
  () => props.value,
  (value) => {
    input.value = value
  }
)
//------------------------------------------------------------------------------------------------------------
//computed
//------------------------------------------------------------------------------------------------------------
/*
const counter: Ref<number> = useState('counter', () => 500)

// computedによりcounter変数の監視が行われる
const doubleCount = computed(() => {
  return counter.value * 2
})
*/
//------------------------------------------------------------------------------------------------------------
// エミット
//------------------------------------------------------------------------------------------------------------
/*
const emits = defineEmits<{ (e: 'update:value', item: any): void }>()
const input = ref(props.value)

function onChange(value: any) {
  input.value = value
  emits('update:value', value)
}
*/

//------------------------------------------------------------------------------------------------------------
// メソッド
//------------------------------------------------------------------------------------------------------------
</script>

<style lang="scss" scoped>
section {
  border: blue 5px solid;
  margin: 10px;
}
p {
  color: red;
}
</style>
