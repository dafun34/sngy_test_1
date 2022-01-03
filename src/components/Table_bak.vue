<template>
  <v-data-table
	v-model="selected"
    :headers="headers"
    :items="occupations"
	:single-select="singleSelect"
    :items-per-page="10"
    class="elevation-1">
	<template v-slot:top>
      <v-switch
        v-model="singleSelect"
        label="Single select"
        class="pa-3"
      ></v-switch>
    </template>
	<template #item.hireDate="{item}">
		<HireDisplay :hireDate="item.hireDate"/>
	</template>

	<template #item.fireDate="{item}"> 
		<FireDisplay :fireDate="item.fireDate"/>
	</template>

    <template #item.salary="{item}">
        {{item.salary}} ₽ ({{item.fraction}}%)
    </template>

	<template #item.base="{value}">
		{{value}} ₽
	</template>

	<template #item.advance="{value}">
		{{value}} ₽
	</template>

	<template v-slot:item.byHours="{item}">
		<v-simple-checkbox
		v-model="item.byHours"
		disabled>
		</v-simple-checkbox>
	</template>

	
  </v-data-table>
</template>./HireDisplay.vue

<script>
import HireDisplay from './HireDisplay.vue'
import FireDisplay from './FireDisplay.vue'
export default {
    name: 'Table',
	components:{
		HireDisplay,
		FireDisplay
	},
    data: () => ({
		
        headers: [
            {text: 'Сотрудник', value: 'name'},
            {text: 'Компания', value: 'companyName'},
            {text: 'Должность', value: 'positionName'},
            {text: 'Дата приёма', value: 'hireDate'},
            {text: 'Дата увольнения', value: 'fireDate'},
            {text: 'Ставка', value: 'salary'},
			{text: 'База', value: 'base'},
			{text: 'Аванс', value: 'advance'},
			{text: 'Почасовая', value: 'byHours'}
            
        ],
        occupations: [
            {
		name: 'Джордж Вашингтон',
		companyName: 'ООО "Синергия"',
		positionName: 'Первый президент США',
		hireDate: '1789-04-30',
		fireDate: '1797-03-04',
		salary: 1000,
		fraction: 100,
		base: 1000,
		advance: 1000,
		byHours: false
	},
	{
		name: 'Ричард I Львиное Сердце',
		companyName: 'ООО "Синергия"',
		positionName: 'Король Англии',
		hireDate: '1189-01-01',
		fireDate: '1199-05-17',
		salary: 1000,
		fraction: 100,
		base: 1000,
		advance: 1000,
		byHours: true
	},
	{
		name: 'Джейсон Стейтем',
		companyName: 'ООО "Синергия"',
		positionName: 'Бейкон',
		hireDate: '1998-09-01',
		fireDate: null,
		salary: 1000,
		fraction: 100,
		base: 1000,
		advance: 1000,
		byHours: false
	},
	{
		name: 'Тарантино К. Дж.',
		companyName: 'ООО "Синергия"',
		positionName: 'Джимми',
		hireDate: '1994-04-15',
		fireDate: null,
		salary: 1000,
		fraction: 100,
		base: 1000,
		advance: 1000,
		byHours: false
	},
	{
		name: 'Камбербэтч Б.',
		companyName: 'ООО "Синергия"',
		positionName: 'Смауг',
		hireDate: '1000-01-01',
		fireDate: '2941-10-09',
		salary: 1000,
		fraction: 100,
		base: 1000,
		advance: 1000,
		byHours: false
	},
	{
		name: 'Крузенштерн И. Ф.',
		companyName: 'ООО "Синергия"',
		positionName: 'Человек и пароход',
		hireDate: '1770-11-08',
		fireDate: null,
		salary: 1000,
		fraction: 100,
		base: 1000,
		advance: 1000,
		byHours: false
	},
	{
		name: 'Бендер С. Р.',
		companyName: '"Planet Express"',
		positionName: 'Робот-сгибальщик',
		hireDate: '2997-03-27',
		fireDate: null,
		salary: 1000,
		fraction: 100,
		base: 1000,
		advance: 1000,
		byHours: true
	}
        ]
    })
}
</script>