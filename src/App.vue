<script setup>
import { RangeNavigatorComponent as EjsRangenavigator,
  DateTime, RangenavigatorSeriesCollectionDirective as ERangenavigatorSeriesCollection,
   RangenavigatorSeriesDirective as ERangenavigatorSeries,AreaSeries, StepLineSeries,
   RangeTooltip
} from "@syncfusion/ej2-vue-charts";
import { provide } from 'vue';

let stockDetails=[
        { date: new Date('2017-01-01'), value: 21 },
        { date: new Date('2018-01-01'), value: 24 },
        { date: new Date('2019-01-01'), value: 36 },
        { date: new Date('2020-01-01'), value: 38 },
        { date: new Date('2021-01-01'), value: 50 },
        { date: new Date('2022-01-01'), value: 52 }           
      ];
      
provide('rangeNavigator', [ DateTime,AreaSeries,StepLineSeries,RangeTooltip ]);
const value = [new Date('2019-01-01'),new Date('2021-01-01')];
const majorGridLines = {width: 4,color: 'green'};
const majorTickLines = {
  width: 3,
  color: 'yellow'
};
const tooltip = { enable: true, displayMode: 'Always'}
</script>

<template>
 <ejs-rangenavigator valueType="DateTime" 
 intervalType="Months" labelFormat="MMM-yy" :value='value'
 :majorGridLines='majorGridLines' :majorTickLines='majorTickLines'
 :tooltip='tooltip' :dataSource='stockDetails'  xName='date' yName='value'
 type='StepLine' >
  <e-rangenavigator-series-collection>
            <e-rangenavigator-series >
            </e-rangenavigator-series>
  </e-rangenavigator-series-collection>
 </ejs-rangenavigator>
</template>

<style>

</style>
