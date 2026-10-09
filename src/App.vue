<script setup lang="ts">
import {ref} from 'vue'
const menu=ref(false)
const links=[['Inicio','#inicio'],['Partidos','#partidos'],['Noticias','#noticias'],['Clasificación','#clasificacion'],['Club','#club']]
const news=[
{tag:'PRIMER EQUIPO',title:'La pasión celeste sigue escribiendo historia',image:'https://images.unsplash.com/photo-1522778119026-d647f0596c20?w=1200&q=80'},
{tag:'ESTADIO',title:'El Estadio Tamaulipas, nuestra casa',image:'https://images.unsplash.com/photo-1574629810360-7efbbe195018?w=900&q=80'},
{tag:'AFICIÓN',title:'La afición: nuestro jugador número doce',image:'https://images.unsplash.com/photo-1459865264687-595c88be72c2?w=900&q=80'}]
const matches=[['JAIBA BRAVA','RIVAL A'],['RIVAL B','JAIBA BRAVA']]
</script>
<template>
<div>
<div class="topbar"><span>TAMPICO · CIUDAD MADERO</span><span>CONCEPTO NO OFICIAL · DEMO</span></div>
<header class="header"><a class="brand" href="#inicio"><span class="crest">JB</span><span>JAIBA BRAVA<small>TAMPICO-MADERO</small></span></a><button class="menu" @click="menu=!menu" :aria-expanded="menu">☰</button><nav :class="{open:menu}"><a v-for="l in links" :key="l[1]" :href="l[1]" @click="menu=false">{{l[0]}}</a></nav><a class="nav-cta" href="#club">CONOCE AL CLUB ↗</a></header>
<main><section id="inicio" class="hero"><div class="hero-content"><span class="eyebrow">ORGULLO · IDENTIDAD · PASIÓN</span><h1>YO SOY<br><em>CELESTE.</em></h1><p>De Tampico y Ciudad Madero para el mundo. No es suerte, es historia.</p><a class="button" href="#partidos">DESCUBRE MÁS ↗</a></div><div class="hero-caption">ESTADIO TAMAULIPAS · NUESTRA CASA</div></section>
<section id="partidos" class="section"><div class="eyebrow">EN LA CANCHA</div><h2>PRÓXIMOS <em>PARTIDOS</em></h2><p class="note">CALENDARIO DEMOSTRATIVO · SIN FECHAS OFICIALES</p><div class="match-grid"><article v-for="(m,i) in matches" :key="i" class="match-card"><div class="match-meta"><span>PRÓXIMO</span><span>POR CONFIRMAR</span></div><div class="teams"><strong>{{m[0]}}</strong><span>VS</span><strong>{{m[1]}}</strong></div><div class="match-foot">INFORMACIÓN POR CONFIRMAR ↗</div></article></div></section>
<section id="noticias" class="section news"><div class="eyebrow">AL DÍA CON EL EQUIPO</div><h2>ACTUALIDAD <em>CELESTE</em></h2><div class="news-grid"><article v-for="n in news" :key="n.title" class="news-card" :style="{backgroundImage:'linear-gradient(0deg,rgba(4,19,31,.94),transparent 85%),url('+n.image+')'}"><div><span class="eyebrow">{{n.tag}} · DEMO</span><h3>{{n.title}}</h3></div></article></div></section>
<section id="clasificacion" class="dark-zone section"><div class="eyebrow">LA COMPETENCIA</div><h2>TABLA DE <em>POSICIONES</em></h2><p>Datos de ejemplo. Se integrará una tabla oficial cuando esté disponible.</p><table><thead><tr><th>#</th><th>CLUB</th><th>PJ</th><th>DG</th><th>PTS</th></tr></thead><tbody><tr v-for="(t,i) in ['JAIBA BRAVA','RIVAL A','RIVAL B']" :key="t"><td>{{i+1}}</td><td>{{t}}</td><td>—</td><td>—</td><td>—</td></tr></tbody></table></section>
<section id="club" class="section about"><div class="eyebrow">MÁS QUE NOVENTA MINUTOS</div><h2>NUESTRO CLUB.<br><em>NUESTRA HISTORIA.</em></h2><p>Dos ciudades, una pasión celeste. Este es un concepto visual independiente, no un sitio oficial del club.</p><a class="button" href="#inicio">VOLVER AL INICIO ↗</a></section></main>
<footer><strong>JAIBA BRAVA</strong><span>NO ES SUERTE, ES HISTORIA.</span><small>Maqueta no oficial. Fotografías genéricas y datos ilustrativos.</small></footer>
</div>
</template>