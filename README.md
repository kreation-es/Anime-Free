<? xml version = "1.0" encoding = "UTF-8"?>
<! DOCTYPE html>
<html b: css = 'false' b: defaultwidgetversion = '2' b: js = 'true' b: layoutsVersion = '3' b: responsive = 'true' expr: dir = 'data: blog.locale.languageDirection' expr: lang = 'data: blog.locale.language' prefix = 'og: http://ogp.me/ns#'>

<! - Anime.xml-free v4.3.0 | Canvas.xml v1.10.0 | github.com/zkreations/canvas.xml ->

<cabeza>
<! - Datos básicos ->
<meta expr: charset = 'data: blog.encoding' />
<meta expr: content = 'data: view.isHomepage? "sitio web": "artículo" 'propiedad =' og: tipo '/>

<! - Ventana de visualización receptiva ->
<meta content = 'width = device-width, initial-scale = 1' name = 'viewport' />

<! - Nombre de la aplicación ->
<meta expr: content = 'data: blog.title' name = 'application-name' />
<meta expr: content = 'data: blog.title' property = 'og: site_name' />

<! - Etiqueta meta de referencia ->
<meta content = 'unsafe-url' name = 'referrer' />

<! - Tipo de tarjeta de twitter ->
<meta content = 'summary_large_image' name = 'twitter: card' />

<! - favicon ->
<link expr: href = 'data: blog.blogspotFaviconUrl' rel = 'icon' type = 'image / x-icon' />

<! - Url canónica ->
<meta expr: content = 'data: view.url.canonical' property = 'og: url' />
<link expr: href = 'data: view.url.canonical' rel = 'canonical' />

<! - Descripcion ->
<b: if cond = 'data: view.description'>
   <meta expr: content = 'data: view.description.escaped' property = 'og: description' />
   <meta expr: content = 'data: view.description.escaped' name = 'description' />
</ b: si>

<b: if cond = 'data: view.isError o data: view.isArchive o data: view.isSearch'>
   <meta content = 'noindex, follow' name = 'robots' />
</ b: si>

<! - Imagen destacada ->
<b: if cond = 'datos: widgets'>
   <b: valores de bucle = 'datos: widgets.Blog.first.posts donde (p => p.featuredImage) map (p => p.featuredImage)' var = 'imageUrl'>
     <meta expr: content = 'resizeImage (data: imageUrl, 1200, "1200: 630")' property = 'og: image' />
   </ b: bucle>
   <meta property = 'og: image: width' content = "1200" />
   <meta property = 'og: image: height' content = "630" />
</ b: si>

<! - Título ->
<b: con valor = 'datos: view.isError? data: messages.theresNothingHere: data: view.title.escaped 'var =' title '>
   <meta expr: content = 'data: title' property = 'og: title' />
   <meta expr: content = 'data: title' name = 'twitter: title' />
   <title> <data: title /> </title>
</ b: con>

<! - Feeds ->
<b: if cond = 'data: blog.feedLinks'>
<b: with value = 'path (data: blog.homepageUrl.canonical, "feeds / posts / default")' var = 'feeds'>
   <link expr: href = 'data: feeds' title = 'Atom 1.0' rel = 'alternate' type = 'application / atom + xml' />
   <link expr: href = 'data: feeds params {alt: "rss"}' title = 'RSS 2.0' rel = 'alternate' type = 'application / rss + xml' />
</ b: con>
</ b: si>

<! - AdSense ->
<b: if cond = 'data: widgets.AdSense.first o data: blog.adsenseClientId'>
   <script async = 'async' src = '// pagead2.googlesyndication.com/pagead/js/adsbygoogle.js' />
</ b: si>

<! - Cuadro de búsqueda de enlaces de sitio ->
<tipo de script = 'aplicación / ld + json'>
{
    "@context": "http://schema.org",
    "@type": "Sitio web",
    "url": "<data: blog.homepageUrl.canonical />",
    "potencialAcción": {
        "@type": "SearchAction",
        "target": "<data: blog.searchUrl />? q = {search_term_string}",
        "query-input": "nombre obligatorio = search_term_string"
    }
}
</script>

<b: comentario> Estilos globales </ b: comentario>
<estilo> / * <! [CDATA [* /
/ *! Fuentes de Google * /
@ font-face {font-family: Oswald; font-style: normal; font-weight: 400; src: local ('Oswald Regular'), local ('Oswald-Regular'), url (https: // fonts. gstatic.com/s/oswald/v16/TK3iWkUHHAIjg752GT8A.woff) formato ('woff'); font-display: fallback} @ font-face {font-family: Oswald; font-style: normal; font-weight: 500; src: formato local ('Oswald Medium'), local ('Oswald-Medium'), url (https://fonts.gstatic.com/s/oswald/v16/TK3hWkUHHAIjg75-6hwTus9E.woff) ('woff'); font-display: fallback} @ font-face {font-family: Oswald; font-style: normal; font-weight: 700; src: local ('Oswald Bold'), local ('Oswald-Bold'), url ( https://fonts.gstatic.com/s/oswald/v16/TK3hWkUHHAIjg75-ohoTus9E.woff) formato ('woff'); font-display: fallback} @ font-face {font-family: Roboto; font-display: auto; estilo de fuente: normal; peso de fuente: 300; src: local ('Roboto Light'),local ('Roboto-Light'), url (https://fonts.gstatic.com/s/roboto/v19/KFOlCnqEu92Fr1MmSU5fBBc-.woff) formato ('woff'); font-display: fallback} @ font-face { font-family: Roboto; font-display: auto; font-style: normal; font-weight: 400; src: local ('Roboto'), local ('Roboto-Regular'), url (https: // fonts. gstatic.com/s/roboto/v19/KFOmCnqEu92Fr1Mu4mxM.woff) formato ('woff'); font-display: fallback} @ font-face {font-family: Roboto; font-display: auto; font-style: normal; font-weight: 500; src: formato local ('Roboto Medium'), local ('Roboto-Medium'), url (https://fonts.gstatic.com/s/roboto/v19/KFOlCnqEu92Fr1MmEU9fBBc-.woff) ( 'woff'); font-display: fallback} @ font-face {font-family: Roboto; font-display: auto; font-style: normal; font-weight: 700; src: local ('Roboto Bold'), local ('Roboto-Bold'), url (https: //fonts.gstatic.com / s / roboto / v19 / KFOlCnqEu92Fr1MmWUlfBBc-.woff) formato ('woff'); font-display: fallback}

/ *!
 * Ballena v1.6.0
 * Copyright 2017-2019 zkreations
 * Desarrollado por Daniel Abel M. (instagram.com/danie.abel)
 * Con licencia de MIT (github.com/zkreations/whale/blob/master/LICENSE)
 * normalize.css v8.0.1 | Licencia MIT | github.com/necolas/normalize.css
 -webkit-search-decoration {-webkit-apariencia: ninguno} :: - botón-cargar-archivo-webkit {-webkit-apariencia: botón; fuente: heredar} resumen {pantalla: elemento de lista} [oculto], plantilla { display: none} / *! End normalize.css * / body {margin: 0; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Símbolo de interfaz de usuario de Segoe"; tamaño de fuente: 1rem; peso de fuente: 400; altura de línea: 1.5; alineación de texto: izquierda} a {color: # 2196f3; decoración de texto: ninguna; color de fondo: transparente} a : hover {color: # 1565c0} a: active, a: focus, a: hover {text-decoration: none; outline-width: 0} a: not ([href]): not ([tabindex]), a: not ([href]): not ([tabindex]): focus, a: not ([href]): not ([tabindex]): hover {color: heredar; text-decoration: none} a: not ([href ]): not ([tabindex]): focus {esquema: 0} dl, ol, ul {padding-left: 0; list-style: none} .h1, .h2, .h3, .h4, .h5 ,. h6,
 
 / *! Spinner de diseño de materiales | codepen.io/zkreations/pen/JwjpMV * /
.circular {-webkit-animation: rotar 1,5 s lineal infinito; animación: rotar 1,5 s lineal infinito; altura: 48 px; posición: relativa; ancho: 48 px; pantalla: bloque; margen izquierdo: automático; margen derecho: automático} .circular .path {-webkit-animation: guión 1.5s entrada-salida infinita; animación: guión 1.5s entrada-salida infinita; relleno: ninguno; trazo: # 999; trazo-dasharray: 1%, 200% ; stroke-dashoffset: 0; stroke-linecap: round; stroke-width: 3} @ - webkit-keyframes rotate {100% {- webkit-transform: rotate (360deg); transform: rotate (360deg)}} @ keyframes rotate {100% {- webkit-transform: rotate (360deg); transform: rotate (360deg)}} @ - webkit-keyframes dash {0% {stroke-dasharray: 1%, 200%; stroke-dashoffset: 0} 50% {stroke-dasharray: 90%, 200%; stroke-dashoffset: -35%} 100% {stroke-dasharray: 90%, 200%; stroke-dashoffset: -124%}} @ fotogramas clave guión {0% {stroke- dasharray: 1%, 200%; stroke-dashoffset: 0} 50% {stroke-dasharray: 90%, 200%; stroke-dashoffset:-35%} 100% {stroke-dasharray: 90%, 200%; stroke-dashoffset: -124%}}

/ *! TinySlider | github.com/ganlanyuan/tiny-slider * /
.tns-gallery, .tns-no-calc {posición: relativa; izquierda: 0} .tns-ovh, .tns-t-subp2 {overflow: hidden} .tns-outside {padding: 0! important} .tns- externo [oculto] {pantalla: ninguno! importante} .tns-externo [aria-controles] ,. tns-externo [acción-datos] {cursor: puntero} .tns-control deslizante> .tns-elemento {-caja-kit-web- sizing: border-box; -moz-box-sizing: border-box; box-sizing: border-box} .tns-horizontal.tns-subpixel {espacio en blanco: nowrap} .tns-horizontal.tns-subpixel>. tns-item {display: inline-block; vertical-align: top; white-space: normal} .tns-horizontal.tns-no-subpixel: after, .tns-t-ct: after {content: ''; display : table; clear: both} .tns-horizontal.tns-no-subpixel> .tns-item {float: left; margin-right: -100%}. tns-gallery {min-height: 1px} .tns-gallery > .tns-item {posición: absoluta; izquierda: -100%; - webkit-transición: transformar 0s, opacidad 0s; -moz-transición: transformar 0s, opacidad 0s; transición: transformar 0s, opacidad 0s}.tns-gallery> .tns-slide-active {posición: relativa; izquierda: unset! important} .tns-gallery> .tns-moving {-webkit-transición: todos los .25; -moz-transición: todos los .25; transición : todos .25s} .tns-lazy-img {-kit-web-transición: opacidad .6s; -moz-transición: opacidad .6s; transición: opacidad .6s; opacidad: .6} .tns-lazy-img.loaded { opacidad: 1} .tns-ah {-kit-web-transición: altura 0s; -moz-transición: altura 0s; transición: altura 0s} .tns-visual-hidden {posición: absoluta; izquierda: -10000em} .tns-transparente {opacidad: 0; visibilidad: oculta} .tns-fadeIn {opacidad: 1; filtro: alfa (opacidad = 100); índice z: 0} .tns-fadeOut, .tns-normal {opacidad: 0; filtro: alfa (opacidad = 0); índice z: -1} .tns-t-subp2 {margen: 0 automático; ancho: 310 px; posición: relativa; alto: 10 px} .tns-t-ct {ancho: 2333.3333333%; ancho : -webkit-calc (100% * 70/3); ancho: -moz-calc (100% * 70/3); ancho: calc (100% * 70/3); posición: absoluta; derecha: 0}. tns-t-ct> div {ancho:1.4285714%; width: -webkit-calc (100% / 70); width: -moz-calc (100% / 70); width: calc (100% / 70); height: 10px; float: left} .carousel, .slider {desbordamiento: oculto; posición: relativa; espacio en blanco: nowrap} .tns-inner {transición: ¡todos 0! importante; cambiará: transform} .tns-gallery> div, .tns-gallery> li {posición : absoluto; transición: transformar 0s, opacidad 0s} .tns-slider {transición: transformar 0s} .carousel__content: not (.tns-slider) .carousel__item {width: 50%; display: inline-block} .slider__content: not ( .tns-slider) .slider__item {display: inline-block; width: 100%} @ media (min-width: 576px) {. carousel__content: not (.tns-slider) .carousel__item {width: 33.333333%}} @ media (min-width: 768px) {. carrusel__content: not (.tns-slider) .carousel__item {width: 20%}} @ media (min-width: 992px) {. carrusel__content: not (.tns-slider) .carousel__item { ancho: calc (20% - 3px)}}-webkit-calc (100% / 70); width: -moz-calc (100% / 70); width: calc (100% / 70); height: 10px; float: left} .carousel, .slider {overflow: oculto; posición: relativa; espacio en blanco: nowrap} .tns-inner {transición: ¡todos 0! importante; cambiará: transform} .tns-gallery> div, .tns-gallery> li {posición: absoluta; transición: transform 0s, opacity 0s} .tns-slider {transición: transform 0s} .carousel__content: not (.tns-slider) .carousel__item {width: 50%; display: inline-block} .slider__content: not (.tns-slider) .slider__item {display: inline-block; width: 100%} @ media (min-width: 576px) {. carousel__content: not (.tns-slider) .carousel__item {width: 33.333333%}} @ media (min-width: 768px) {. Carousel__content: not (.tns-slider) .carousel__item {width: 20%}} @ media (min-width: 992px) {. Carousel__content: not (.tns-slider) .carousel__item {width: calc (20 % - 3px)}}-webkit-calc (100% / 70); width: -moz-calc (100% / 70); width: calc (100% / 70); height: 10px; float: left} .carousel, .slider {overflow: oculto; posición: relativa; espacio en blanco: nowrap} .tns-inner {transición: ¡todos 0! importante; cambiará: transform} .tns-gallery> div, .tns-gallery> li {posición: absoluta; transición: transform 0s, opacity 0s} .tns-slider {transición: transform 0s} .carousel__content: not (.tns-slider) .carousel__item {width: 50%; display: inline-block} .slider__content: not (.tns-slider) .slider__item {display: inline-block; width: 100%} @ media (min-width: 576px) {. carousel__content: not (.tns-slider) .carousel__item {width: 33.333333%}} @ media (min-width: 768px) {. Carousel__content: not (.tns-slider) .carousel__item {width: 20%}} @ media (min-width: 992px) {. Carousel__content: not (.tns-slider) .carousel__item {width: calc (20 % - 3px)}}10px; float: left} .carousel, .slider {desbordamiento: oculto; posición: relativa; espacio en blanco: nowrap} .tns-inner {transición: todos 0s! Important; will-change: transform} .tns-gallery> div , .tns-gallery> li {posición: absoluta; transición: transformar 0s, opacidad 0s} .tns-slider {transición: transformar 0s} .carousel__content: not (.tns-slider) .carousel__item {ancho: 50%; mostrar: inline-block} .slider__content: not (.tns-slider) .slider__item {display: inline-block; width: 100%} @ media (min-width: 576px) {. carrusel__content: not (.tns-slider) .carousel__item {width: 33.333333%}} @ media (min-width: 768px) {. carousel__content: not (.tns-slider) .carousel__item {width: 20%}} @ media (min-width: 992px) {. carrusel__content: not (.tns-slider) .carousel__item {width: calc (20% - 3px)}}10px; float: left} .carousel, .slider {desbordamiento: oculto; posición: relativa; espacio en blanco: nowrap} .tns-inner {transición: todos 0s! Important; will-change: transform} .tns-gallery> div , .tns-gallery> li {posición: absoluta; transición: transformar 0s, opacidad 0s} .tns-slider {transición: transformar 0s} .carousel__content: not (.tns-slider) .carousel__item {ancho: 50%; mostrar: inline-block} .slider__content: not (.tns-slider) .slider__item {display: inline-block; width: 100%} @ media (min-width: 576px) {. carrusel__content: not (.tns-slider) .carousel__item {width: 33.333333%}} @ media (min-width: 768px) {. carousel__content: not (.tns-slider) .carousel__item {width: 20%}} @ media (min-width: 992px) {. carrusel__content: not (.tns-slider) .carousel__item {width: calc (20% - 3px)}}will-change: transform} .tns-gallery> div, .tns-gallery> li {posición: absoluta; transición: transformar 0s, opacidad 0s} .tns-slider {transición: transformar 0s} .carousel__content: not (.tns- slider) .carousel__item {width: 50%; display: inline-block} .slider__content: not (.tns-slider) .slider__item {display: inline-block; width: 100%} @ media (min-width: 576px) { .carousel__content: not (.tns-slider) .carousel__item {width: 33.333333%}} @ media (min-width: 768px) {. carousel__content: not (.tns-slider) .carousel__item {width: 20%}} @ media (min-width: 992px) {. carrusel__content: not (.tns-slider) .carousel__item {width: calc (20% - 3px)}}will-change: transform} .tns-gallery> div, .tns-gallery> li {posición: absoluta; transición: transformar 0s, opacidad 0s} .tns-slider {transición: transformar 0s} .carousel__content: not (.tns- slider) .carousel__item {width: 50%; display: inline-block} .slider__content: not (.tns-slider) .slider__item {display: inline-block; width: 100%} @ media (min-width: 576px) { .carousel__content: not (.tns-slider) .carousel__item {width: 33.333333%}} @ media (min-width: 768px) {. carousel__content: not (.tns-slider) .carousel__item {width: 20%}} @ media (min-width: 992px) {. carrusel__content: not (.tns-slider) .carousel__item {width: calc (20% - 3px)}}slider__item {display: inline-block; width: 100%} @ media (min-width: 576px) {. carousel__content: not (.tns-slider) .carousel__item {width: 33.333333%}} @ media (min-width: 768px ) {. carousel__content: not (.tns-slider) .carousel__item {width: 20%}} @ media (min-width: 992px) {. carrusel__content: not (.tns-slider) .carousel__item {width: calc (20%) - 3px)}}slider__item {display: inline-block; width: 100%} @ media (min-width: 576px) {. carousel__content: not (.tns-slider) .carousel__item {width: 33.333333%}} @ media (min-width: 768px ) {. carousel__content: not (.tns-slider) .carousel__item {width: 20%}} @ media (min-width: 992px) {. carrusel__content: not (.tns-slider) .carousel__item {width: calc (20%) - 3px)}}

/* Estilo
-------------------------------------- * /
html {
   tamaño de fuente: 12px;
}
cuerpo {
   overflow-wrap: palabra de ruptura;
   ajuste de palabra: romper-palabra
}
/* defecto
-------------------------------------- * /
a {
   peso de fuente: 400;
    transición: color .3s;
}
:: - selección-moz {
    color: #ffffff;
}
:: selección {
    color: #ffffff;
}
/ * Arreglar el renderizado
-------------------------------------- * /
.nav__menu *,
.gallery * {
   -webkit-backface-visibilidad: oculto;
           visibilidad del reverso: oculto;
}
.plantilla {
    altura mínima: 100vh;
}
/ * Fontawesome
-------------------------------------- * /
.fab, .fal, .far, .fas {
    margen derecho: 4px;
    pantalla: bloque en línea;
    estilo de fuente: normal;
    variante de fuente: normal;
    renderizado de texto: automático;
    altura de línea: 1;
}
.fa-mn {
   margen derecho: 0;
}
/ * ayudantes
-------------------------------------- * /
.pl-none {
    padding-left: 0! important;
}
.pr-none {
    padding-right: 0! important;
}
.ml-none {
    margen izquierdo: 0! importante;
}
.mr-none {
    margen derecho: 0! importante;
}
.ml-auto {
    margin-left: auto! important;
}
.mr-auto {
    margin-right: auto! important;
}
[clase * = flx-] {
    pantalla: -ms-flexbox! important;
    pantalla: flex! important;
}
.flx-xyc,
.flx-yc {
    -ms-flex-align: center! important;
        alinear-elementos: centro! importante;
}
.flx-xyc,
.flx-xc {
    -ms-flex-pack: centro! importante;
        justificar-contenido: centro! importante;
}
.estirarse {
    arriba: 0; izquierda: 0; derecha: 0; abajo: 0;
}
.No evento {
    eventos de puntero: ninguno;
}
/ * Fotogramas clave
-------------------------------------- * /
@ -webkit-keyframes dropdown {
    de {
        -webkit-transform: translateY (-1rem) scale (.9);
                transformar: translateY (-1rem) scale (.9);
        opacidad: 0;
    }
    para {
        -webkit-transform: translateY (0) scale (1);
                transformar: translateY (0) scale (1);
        opacidad: 1;
    }
}
@keyframes menú desplegable {
    de {
        -webkit-transform: translateY (-1rem) scale (.9);
                transformar: translateY (-1rem) scale (.9);
        opacidad: 0;
    }
    para {
        -webkit-transform: translateY (0) scale (1);
                transformar: translateY (0) scale (1);
        opacidad: 1;
    }
}
@ -webkit-keyframes fade {
    de {
        opacidad: 0;
    }
    para {
        opacidad: 1;
    }
}
@keyframes se desvanecen {
    de {
        opacidad: 0;
    }
    para {
        opacidad: 1;
    }
}
/ * Plantilla de interfaz de usuario
-------------------------------------- * /
/* Aporte */
.form-input {
   acolchado: .8em 1em;
   borde: rgba sólido de 2px (0, 0, 0, 0.1);
   transición: borde .2s;
   sombra de caja: 0 0 transparente;
   fondo: #fff;
   altura de línea: 1;
}
.form-input,
.form-input :: - webkit-input-placeholder {
   peso de fuente: 500;
   tamaño de fuente: 1.1rem;
   color: rgba (0, 0, 0, .5);
}
.form-input,
.form-input :: - moz-placeholder {
   peso de fuente: 500;
   tamaño de fuente: 1.1rem;
   color: rgba (0, 0, 0, .5);
}
.form-input,
.form-input: -ms-input-placeholder {
   peso de fuente: 500;
   tamaño de fuente: 1.1rem;
   color: rgba (0, 0, 0, .5);
}
.form-input,
.form-input :: - ms-input-placeholder {
   peso de fuente: 500;
   tamaño de fuente: 1.1rem;
   color: rgba (0, 0, 0, .5);
}
.form-input,
.form-input :: placeholder {
   peso de fuente: 500;
   tamaño de fuente: 1.1rem;
   color: rgba (0, 0, 0, .5);
}
/* Botón */
.btn {
    color: # 444444;
    acolchado: 1em;
    opacidad: 1;
    transición: opacidad .3s;
    color de fondo: # f2f2f2;
    radio del borde: 3px;
}
.btn-ghost {
    fondo: transparente;
    borde: rgba sólido de 1px (0,0,0, .06);
}
.btn: hover {
   opacidad: 0,75;
   color: # 444444;
}
.btn [clase * = 'bg-'],
.btn [clase * = 'skin-bg'] {
   color: #fff;
}
.btn [clase * = 'bg -']: desplazarse,
.btn [class * = 'skin-bg']: hover {
   color: #fff;
}
.btn-border {
   fondo: transparente;
   borde: rgba sólido de 2px (0, 0, 0, 0.1);
   color: # 757575;
   transición: color .3s, borde .3s;
   peso de fuente: 500;
   altura de línea: 1;
   pantalla: bloque en línea;
}
.btn-border: hover {
   color del borde: rgba (0, 0, 0, 0.15);
   color: # 262626;
}
/ * Galería * /
.gallery {
    margen inferior: 1rem;
}
.gallery__href {
   posición: relativa;
   bloqueo de pantalla;
   desbordamiento: oculto;
   alineación de texto: centro;
}
.gallery__title {
   espacio en blanco: inicial;
   posición: absoluta;
   bloqueo de pantalla;
   izquierda: 0;
   derecha: 0;
   abajo: 0;
   peso de fuente: 500;
   tamaño de fuente: 1.1rem;
   índice z: 10;
   color: #fff;
   acolchado: 1.5rem;
   imagen de fondo: degradado lineal (transparente, rgba (0, 0, 0, 0.85));
   transición: color .3s;
   sombra de texto: 0 2px 2px rgba (0, 0, 0, 0.2);
}
.gallery__image img,
.gallery__image {
    ancho: 100%;
}
.gallery__image {
    posición: relativa;
    índice z: 5;
}
.gallery__href :: before {
    duración de la transición: .5 s! importante;
}
/ * if => está relacionado con la publicación * /
.rel__date {
    bloqueo de pantalla;
    margen superior: .5rem;
    tamaño de fuente: 1rem;
    opacidad: 0,75;
}
.rel__title {
    tamaño de fuente: 1.2rem;
}
/*Carrusel*/
.carousel__controls {
    posición: absoluta;
    arriba: 0; abajo: 0;
    opacidad: 0;
    índice z: 10;
    acolchado: 1.2rem;
    tamaño de fuente: 18px;
    cursor: puntero;
    transición: fondo .3s, opacidad .3s;
    fondo: rgba (255,255,255, .25);
    color: # 262626;
}
.carousel__controls: hover {
    fondo: rgba (255,255,255, .75)
}
.carousel: hover .carousel__controls {opacity: 1;}
.controls__prev {izquierda: 0}
.controls__next {derecha: 0}
/ * Tarjetas * /
.tarjeta {
    margen inferior: 1rem;
}
.card__data {
    acolchado: 1.2rem;
}
.card__authorName {
    peso de fuente: 500;
}
.card__descripcion: no (: último hijo),
.card__meta: no (: último hijo),
.card__header: not (: last-child) {
    fondo acolchado: 1rem;
}
.card__icon {
    posición: absoluta;
    abajo: 0;
    tamaño de fuente: 1.2rem;
    derecha: 0;
    acolchado: 1.2rem;
    índice z: 1;
}
.pagerPost,
.post-related,
.postComments,
.shareButtons: not (.card__share) {
    acolchado superior: 1.5rem;
}
.card__title {
    tamaño de fuente: 1.4rem;
    margen inferior: 0;
    peso de fuente: 400;
}
.card__data {
    posición: relativa;
}
.card__authorImage {
    desbordamiento: oculto;
    radio de borde: 50%;
    margen derecho: .5rem;
}
.Image__full {
    margen izquierdo: -1rem;
    margen derecho: -1rem;
}
.card__image {
    posición: relativa;
}
.card__image,
.card__image img {
    ancho: 100%;
    bloqueo de pantalla;
}
.card__item {
    peso de fuente: 500;
}
time.card__item {
    text-transform: capitalizar;
}
.card__item,
.card__item * {
    transición: color .3s;
}
.card__item: not (: last-child) {
    margen derecho: .75rem;
}
.card__descripcion {
    tamaño de fuente: 1.1rem;
}

.card__readMore :: before {
    pantalla: ninguna;
}
.card__image: hover .card__readMore :: before {
    bloqueo de pantalla;
    modo de relleno de animación: ambos! importante;
}
/ * if => es Buscar * /
.search-img {
    flotador izquierdo;
    margen derecho: 1rem;
    margen inferior: 1rem;
}
.card-search .card__header {
    fondo acolchado: .5rem! important;
}
.card-search .card__title {
    tamaño de fuente: 1.1rem;
    familia de fuentes: heredar;
}
.card-search .card__title a {
    peso de fuente: 500;
}
.card__readMore {
    color: #fff;
    tamaño de fuente: 24px;
    margen: 0;
}
.card__readMore,
.gallery__href :: antes,
.card__overlay {
    opacidad: 0;
    transición: opacidad .2s;
    índice z: 10;
}
.card__image: hover .card__readMore {
    opacidad: 1;
}
.gallery__href: hover :: before,
.card__image: hover .card__overlay {
    opacidad: 0,75;
}
.card__readMore,
.card__overlay,
.gallery__href :: antes,
.card__overlay :: before {
    posición: absoluta;
    arriba: 0;
    izquierda: 0;
    ancho: 100%;
    altura: 100%;
}
.gallery__href :: antes,
.card__overlay :: before {
    contenido: "";
}
/ * botones de compartir * /
.articleTags .btn,
.shareFeatured .btn,
.shareButtons .btn {
    margen: 0 6px 6px 0;
}
.skin-i {
    color: rgba (0,0,0,0.5);
}
/ * FeatureTags
-------------------------------------------------- - * /
.ftag-content {
   posición: absoluta;
   índice z: 20;
   pantalla: bloque en línea;
   arriba: 1rem;
   izquierda: 1rem;
}
.ftag-name {
   text-transform: capitalizar;
   flotador izquierdo;
   decoración de texto: ninguna;
   cursor: puntero;
   transición: fondo .3s;
   espacio en blanco: nowrap;
   acolchado: .7rem;
   color: #fff;
   radio del borde: 2px;
   margen: 2px;
   tamaño de fuente: 13px;
   altura de línea: 1;
}
.ftag-name: hover {
    fondo: # 262626;
    color: #fff;
}
/ * Paleta de colores (500)
-------------------------------------- * /
/* Color */
.color-fern {
    color: # 67B36A;
}
.color-ocean-green {
    color: # 409C75;
}
.color-eastern-blue {
    color: # 23A6B3;
}
.color-san-marino {
    color: # 42689C;
}
.color-blue-violet {
    color: # 655FB3;
}
/* Fondo */
.bg-fern {
    color de fondo: # 67B36A;
}
.bg-ocean-green {
    color de fondo: # 409C75;
}
.bg-eastern-blue {
    color de fondo: # 23A6B3;
}
.bg-san-marino {
    color de fondo: # 42689C;
}
.bg-blue-violet {
    color de fondo: # 655FB3;
}
/ *! Artículo v1.1.0
-------------------------------------- * /
.drop-caps: first-letter {
    flotador izquierdo;
    tamaño de fuente: 70px;
    altura de línea: 60px;
    acolchado superior: .5rem;
    padding-right: 1rem;
    peso de fuente: 300;
    familia de fuentes: Georgia, serif;
}
/*Dirigir*/
.dirigir {
    tamaño de fuente: 1.4rem;
    peso de fuente: 300;
}
/ * Cuadrícula de párrafo * /
.pgrid> [clase * = "col-"] {
    margen inferior: 24px;
}
/ * Blockquote * /
blockquote {
    borde izquierdo: 3px sólido;
    acolchado: 1rem 1.5rem;
    peso de fuente: 400;
    margen inferior: 0;
    margen superior: 0;
    margen izquierdo: 1rem;
    tamaño de fuente: 1.2rem;
    posición: relativa;
}
blockquote footer {
    bloqueo de pantalla;
    margen superior: .5rem;
    tamaño de fuente: 1rem;
    opacidad: .8;
}
blockquote footer :: before {
    contenido: "\ 2014 \ 00A0";
}
blockquote: before {
    opacidad: .5;
    contenido: """;
    tamaño de fuente: 4rem;
    margen derecho: .25em;
    flotador izquierdo;
    altura de línea: 1;
    altura: 22px;
}
/* Pestañas */
.wjs-item {
    pantalla: bloque en línea;
    acolchado: 1rem;
    espacio en blanco: nowrap;
    peso de fuente: 500;
    duración de la transición: 0 s;
}
.wjs-item,
.wjs-item: hover {
    color: # 757575;
}
.wjs-item.is-active {
    color: #fff;
}
.wjs-panel {
    acolchado: 1rem;
}
/ * si => es vertical * /
.tab-vertical .wjs-item {
    bloqueo de pantalla;
}
.tab-vertical {
    pantalla: -ms-flexbox;
    pantalla: flex;
}
/* Revelación */
.wjs-spoiler,
.accordion-item {
    margen inferior: 5px;
}
.wjs-botón,
.accordion-title {
    acolchado: .8rem 1rem;
    cursor: puntero;
    bloqueo de pantalla;
    peso de fuente: 500;
    color: # 262626;
    fondo: # f3f3f3;
    radio del borde: 2px;
    ancho: 100%;
    alineación de texto: izquierda;
    -webkit-user-select: ninguno;
       -moz-user-select: ninguno;
        -ms-user-select: ninguno;
            selección de usuario: ninguno;
}
.wjs-button: desplazarse,
.accordion-title: hover {
    opacidad: 0,9;
}
.wjs-contenedor,
.accordion-content {
    altura: 0;
    padding-right: 1rem;
    padding-left: 1rem;
    desbordamiento: oculto;
    -webkit-transform: translateY (-1rem);
            transformar: translateY (-1rem);
}
.wjs-container.is-active,
.accordion-item.is-active .accordion-content {
    altura: auto;
    acolchado superior: 1rem;
    fondo acolchado: 1rem;
    -webkit-transform: translateY (0);
            transformar: translateY (0);
    transición: -webkit-transform .3s;
    transición: transformar .3s;
    transición: transform .3s, -webkit-transform .3s;
}
/ * Separadores * /
.divider, [class * = "divisor-"] {
    bloqueo de pantalla;
    acolchado superior: 2rem;
    margen inferior: 2rem;
    posición: relativa;
}
[clase * = "divisor -"] :: antes {
    contenido: "";
    bloqueo de pantalla;
}
.divider {
    borde inferior: 2px rgba sólido (0, 0, 0, 0.15);
}
.divider-dotted {
    borde inferior: rgba punteado de 2px (0, 0, 0, 0.15);
}
.divider-dashed {
    borde inferior: rgba discontinuo de 2px (0, 0, 0, 0.15);
}
.divider-shadow {
    sombra de cuadro: 0 12px 15px -10px rgba (0, 0, 0, 0.4);
    borde inferior: rgba sólido de 2px (0, 0, 0, 0.4);
}
.divider-double {
    borde inferior: 6px doble rgba (0, 0, 0, 0.15);
}
.divider-ribbon :: before {
    altura: 10px;
    fondo: gradiente lineal repetido (135deg, transparente, transparente 5px, rgba (0, 0, 0, 0.1) 5px, rgba (0, 0, 0, 0.1) 10px) transparente;
}
.divider-gradient :: before {
    altura: 2px;
    fondo: degradado lineal (a la derecha, transparente, rgba (0, 0, 0, 0.15), transparente);
}
/ * Alertas * /
.alerta {
    color de fondo: # f3f3f3;
    acolchado: 1.5rem;
    color: rgba (0, 0, 0, 0,75);
    margen inferior: 5px;
}
.alert-success {
    color de fondo: # b2d9b4;
}
.alert-warning {
    color de fondo: # f1e2b9;
}
.alert-danger {
    color de fondo: # ecb9c1;
}
/ * Modificadores de alertas * /
.Blog> .alert {
    margen inferior: 1rem;
}
/*Video*/
video {
    color de fondo: # 161616;
}
/*audio*/
audio {
    bloqueo de pantalla;
    ancho: 100%;
}
/ * Alinear imagen * /
[class * = 'align-image-'] {
    margen superior: .5em;
    margen inferior: .5em;
}

.align-image-left {
    claro: izquierda;
    flotador izquierdo;
    margen derecho: 1em;
}
.align-image-right {
    claro: correcto;
    flotar derecho;
    margen izquierdo: 1em;
}
/*Captura de imagen*/
.Image__caption figcaption {
    acolchado: 1rem;
    tamaño de fuente: 12px;
    borde inferior: 1px sólido rgba (0, 0, 0, .05);
    alineación de texto: centro;
}
/ * Cubierta de pie de imagen * /
.Image__textCover {
    posición: relativa;
}
.Image__textCover figcaption {
    posición: absoluta;
    arriba: 0;
    izquierda: 0;
    ancho: 100%;
    altura: 100%;
    acolchado: 2rem;
    fondo: rgba (0, 0, 0, 0.5);
    color: #fff;
}
/ * Encabezado
-------------------------------------- * /
.nav-search-bg {
    -webkit-animation: fundido .5s;
            animación: fade .5s;
    posición: fija;
    índice z: 9995;
    fondo: rgba (0, 0, 0, 0.9);
}
.post-body img [src * = "? destacado = común"],
.post-body img [src * = "? destacado = completo"],
.nav-search-bg,
.search-container {
    pantalla: ninguna;
}
.nav-search.is-active .search-container,
.nav-search.is-active + .nav-search-bg {
    bloqueo de pantalla;
}
.search-container {
    posición: fija;
    arriba: 50%;
    izquierda: 50%;
    -webkit-transform: traducir (-50%, - 50%);
            transformar: traducir (-50%, - 50%);
    índice z: 9999;
}
.search-container input {
    acolchado: 1.5rem 1.8rem;
    fondo: transparente;
    ancho: 300px;
    color: #fff;
    tamaño de fuente: 1.4rem;
    will-change: transform, opacity;
    borde: 4px sólido;
}
.search-container input :: - webkit-input-placeholder {
    color: #fff;
    tamaño de fuente: 1.4rem;
}
.search-container input :: - moz-placeholder {
    color: #fff;
    tamaño de fuente: 1.4rem;
}
.search-container input: -ms-input-placeholder {
    color: #fff;
    tamaño de fuente: 1.4rem;
}
.search-container input :: - ms-input-placeholder {
    color: #fff;
    tamaño de fuente: 1.4rem;
}
.search-container input :: placeholder {
    color: #fff;
    tamaño de fuente: 1.4rem;
}
.search-btn {
    margen izquierdo: automático;
    cursor: puntero;
    tamaño de fuente: 1.2rem;
}
.header__wrapper {
    acolchado superior: 1.5rem;
    fondo acolchado: 1.5rem;
}
.logo__descripcion {
    peso de fuente: 500;
    tamaño de fuente: 1rem;
    acolchado superior: .2rem;
    bloqueo de pantalla;
}
.logo__title {
    margen inferior: 0;
    tamaño de fuente: 2rem;
    altura de línea: 1,2;
}
.logo__link {
    peso de fuente: 700;
    pantalla: bloque en línea;
}
/* Menú principal
-------------------------------------- * /
/ * Menú * /
.header__nav {
   posición: relativa;
   índice z: 100;
}
.nav__menu {
   caja de sombra: 0px 1px 6px rgba (0, 0, 0, 0.15);
}
.nav__menu a {
   acolchado: 1.4rem 1.2rem;
   peso de fuente: 500;
   espacio en blanco: nowrap;
   transformación de texto: mayúsculas;
   tamaño de fuente: 1.1rem;
   posición: relativa;
   índice z: 1;
}
.nav__menu ul a {
   acolchado superior: 1.2rem;
   fondo acolchado: 1.2rem;
   transición: fondo .3s;
}
.nav__menu ul> li: hover> a {
    fondo: rgba (255,255,255, .15);
}
.nav__menu .is-parent> a> span.is-arrow :: after,
.nav__menu ul .is-parent> a> span.is-arrow :: after {
   borde: sólido de 2px;
   ancho: 8px;
   altura: 8px;
   margen superior: -3px;
   -webkit-transform: rotar (45 grados) translateZ (0);
   transformar: rotar (45 grados) translateZ (0);
   margen izquierdo: .75rem;
   transición: -webkit-transform .3s;
   transición: transformar .3s;
   transición: transform .3s, -webkit-transform .3s;
}
/ * Alternar * /
.nav__toggle - icon {
   ancho: 22px;
   posición: relativa;
   índice z: 80;
   altura: 12px;
   cursor: puntero;
   bloqueo de pantalla;
}
.nav__toggle - intervalo de iconos: después,
.nav__toggle - intervalo de icono: antes de {contenido: "";}
.nav__toggle - intervalo de iconos, .nav__toggle - intervalo de iconos :: después, .nav__toggle - intervalo de iconos :: antes {
   posición: absoluta;
   izquierda: 0;
   bloqueo de pantalla;
   altura: 2px;
   ancho: 100%;
   transición: .3s superior, .3s inferior, opacidad .3s, -webkit-transform .3s;
   transición: transformar .3s, superior .3s, inferior .3s, opacidad .3s;
   transición: transformar .3s, superior .3s, inferior .3s, opacidad .3s, -webkit-transform .3s;
}
.nav__toggle - ícono span :: before {top: -6px;}
.nav__toggle - intervalo de icono :: después de {parte inferior: -6px;}
.nav__toggle - intervalo de iconos {
   arriba: 50%;
   margen superior: -1px;
}
.nav__toggle.is-active .nav__toggle - intervalo de iconos {
   retardo de transición: .22s;
   función de tiempo de transición: facilidad;
   -webkit-transform: translate3d (0,0,0) rotate (-45deg);
           transformar: translate3d (0,0,0) rotate (-45deg);
}
.nav__toggle.is-active .nav__toggle - icon span :: before {
   arriba: 0;
   transición: .1s superior facilitan .16s, -webkit-transform .13s facilitan .25s;
   transición: .1s superiores facilitan .16s, transforman .13s facilitan .25s;
   transición: .1s superiores facilitan .16s, transforman .13s facilitan .25s, -webkit-transform .13s facilitan .25s;
   -webkit-transform: rotar (-90 grados);
           transformar: rotar (-90 grados);
}
.nav__toggle.is-active .nav__toggle - icon span :: after {
   abajo: 0;
   opacidad: 0;
   transición: fondo .3s, opacidad .1s lineal .1s;
}
.nav__toggle {padding: 1.5rem 0;}
/* Diseño
-------------------------------------- * /
.template-box {
    caja-sombra: 0 0 8px rgba (0, 0, 0, 0.2), 0 0 25px rgba (0, 0, 0, 0.05);
}
.principal {
    acolchado superior: 1rem;
    fondo acolchado: 1rem;
}
. caja de piel,
.principal {
    acolchado: 1rem;
}
.main__general .widget: último hijo {
    margen inferior: 1rem;
}
.principal,
.header .header__nav,
.header__wrapper {
    padding-right: 1rem;
    padding-left: 1rem;
}
.main__blog,
.encabezamiento,
.pie de página,
.principal {
    ancho: 100%;
}
.Blog {
    posición: relativa;
    margen inferior: 1.5rem;
}
.blog: no (.showSidebar) {
    ancho: 100%;
}
.col-5ta {
    -ms-flex: 0 0 20%;
    flexión: 0 0 20%;
    ancho máximo: 20%;
}
/ * Widgets
-------------------------------------- * /
# LinkList200,
# LinkList210,
encabezado .widget {
    padding: 0! important;
    caja-sombra: 0 0 transparente! importante;
    fondo: ninguno transparente! importante;
}
# LinkList210,
encabezado .widget,
# footer-copyright .widget,
#footerLinks .widget {
    margen: 0! importante;
}
header .widget-title {
    pantalla: ninguna;
}
.widget {
   ancho: 100%;
}
.widget-title {
    margen inferior: 1rem;
    posición: relativa;
}
.nombre del widget {
    pantalla: bloque en línea;
    acolchado: 1.1rem;
    tamaño de fuente: 1rem;
    transformación de texto: mayúsculas;
    peso de fuente: 500;
}
.widget-more {
    posición: absoluta;
    arriba: 0;
    derecha: 0;
    abajo: 0;
}
.widget-more-item {
    tamaño de fuente: 1rem;
    padding-right: 1.1rem;
    padding-left: 1.1rem;
    transformación de texto: mayúsculas;
    peso de fuente: 500;
    transición: acolchado .3s;
    will-change: paddding;
}
.widget-more-item: hover {
    relleno a la izquierda: 1.5rem;
    padding-right: 1.5rem;
}
.widget-content {
    ancho: 100%;
}
.artículo: no (: último hijo),
.widget: no (: último hijo) {
    margen inferior: 1rem;
}
/ *
=> Buscar
* /
.form-info {
    margen inferior: 1rem;
    tamaño de fuente: 1.1rem;
}
.searchForm__input {
    border-right: 0 ninguno;
}
.searchForm__button {
    radio de borde: 0;
    tamaño de fuente: 1.2rem;
    acolchado: 1rem;
}
.searchForm__button [class * = fa-] {
    margen: 0;
    ancho: 1.25em;
}
/ *
=> Etiquetas
* /
.tagsList__link {
    acolchado: 1rem 1.2rem;
    margen derecho: 5px;
    margen inferior: 5px;
}
.tags-list__num {
    peso de fuente: 700;
    opacidad: .5;
    margen izquierdo: 5px;
}
.tagsList - lista .tags-list__num {
    flotar derecho;
}
.tagsList - lista .tagsList__link {
    ancho: 100%;
    margen derecho: 0;
    alineación de texto: izquierda;
}
/ *
=> Publicaciones populares
* /
.hotPosts__image {
    ancho: 75px;
    margen derecho: 1rem;
}
.hotPosts__content: not (: último hijo) {
    margen inferior: 1rem;
}
.hotPosts__title {
    tamaño de fuente: 1.1rem;
    margen inferior: .5rem;
}
.hotPosts__title a {
    color: # 262626;
}
.hotPosts__snippet {
    peso de fuente: 400;
    color: # 767676;
}
/ *
=> Publicación destacada
* /
.featuredPost-data .card__title: not (: last-child) {
    fondo acolchado: 1rem;
}
/ *
=> Imagen
* /
.header .imgImage {
    ancho: 100%;
}
.imgCaption {
    margen superior: 1rem;
    bloqueo de pantalla;
    margen inferior: 0;
}
/ * if => encabezado * /
header .widget.Image {
    posición: relativa;
}
header .imgCaption {
    posición: absoluta;
    derecha: 1.5rem;
    abajo: 1.5rem;
    fondo: rgba (0, 0, 0, 0,75);
    color: #fff;
    acolchado: 1rem 1.2rem;
    radio del borde: 4px;
}
/ *
=> Secciones WJS
* /
.wjs-section {
    margen inferior: -1rem;
}

/ * Pie de página
-------------------------------------- * /
.footer__copy {
    alineación de texto: centro;
}
.copy__date {
    pantalla: bloque en línea;
    tamaño de fuente: 1.6rem;
    peso de fuente: 500;
    altura de línea: 1;
}
.copy__attribution {
    transformación de texto: mayúsculas;
    tamaño de fuente: 12px;
    peso de fuente: 500;
}
.copy__attribution a {
    peso de fuente: 700;
}
.footer__primary {
    estilo de borde inferior: sólido;
    border-bottom-width: 2px;
}
.socialList-item: not (: last-child) {
    margen derecho: .75rem;
}
.socialList-item {
    tamaño de fuente: 1.5rem;
}
/ * Sin JS
-------------------------------------- * /
.no-js .wjs-sección,
.no-js .circular {
    pantalla: ninguna;
}

/* Preguntas de los medios
-------------------------------------- * /
@media (ancho máximo: 991px) {
    .nav__menu {
        posición: fija;
        arriba: 0;
        ancho mínimo: 260px;
        ancho máximo: 80vw;
        pantalla: ninguna;
        izquierda: 0;
        abajo: 0;
        índice z: 9001;
        pantalla: ninguna;
    }
    .nav__menu {
        espacio en blanco: normal;
    }
    .nav__menu.is-active {
        bloqueo de pantalla;
    }
}
@media (ancho máximo: 767px) {
   .socialList {
       fondo acolchado: 1rem;
       acolchado superior: 1rem;
       -ms-flex-pack: centro;
           justificar-contenido: centro;
   }
   .footer__copy {
      fondo acolchado: 1rem;
   }
}
@media (ancho máximo: 575px) {
   .footerLink {
      acolchado: 1.2rem;
      ancho: 100%;
      alineación de texto: centro;
      margen inferior: .5rem;
      fondo: rgba (0, 0, 0, 0.5);
   }
   .footerLink: no (: último hijo) {
      margen inferior: .5rem;
   }
}
/ * Dispositivos pequeños * /
@media (ancho mínimo: 576px) {
    .card__descripcion: no (: último hijo),
    .card__meta: no (: último hijo),
    .card__header: not (: last-child) {
        fondo acolchado: 1.4rem;
    }
   .nav__menu {
      ancho: auto;
   }
   .col-5ta-sm {
      -ms-flex: 0 0 20%;
      flexión: 0 0 20%;
      ancho máximo: 20%;
   }
   .footerLink: no (: último hijo) {
      margen derecho: 1rem;
   }
}
/ * Dispositivos medianos * /
@media (ancho mínimo: 768px) {
    .col-5ta-md {
        -ms-flex: 0 0 20%;
        flexión: 0 0 20%;
        ancho máximo: 20%;
    }
    .search-container input {
        ancho: 600px;
    }
    html {
        tamaño de fuente: 14px;
    }
    .footer__copy {
        alineación de texto: derecha;
    }
}
/ * Dispositivos grandes * /
@media (ancho mínimo: 992px) {
   .layout-box {
      padding-right: 1.5rem;
      relleno a la izquierda: 1.5rem;
   }
   .nav__menu {
      sombra de caja: 0 0 transparente;
   }
   .blog {margin-bottom: 0;}
   .nav__toggle {
      pantalla: ninguna;
   }
   .nav__menu> li: hover> a> .is-arrow :: after {
      -webkit-transform: rotate (-45deg) translateZ (0);
              transformar: rotar (-45deg) translateZ (0)
   }
   .nav__menu ul li: hover> a> .is-arrow :: after {
      -webkit-transform: rotate (135deg) translateZ (0);
              transformar: rotar (135deg) translateZ (0)
   }
   .nav__menu li> ul {
      caja de sombra: 0px 1px 6px rgba (0, 0, 0, 0.15);
   }
   .skin-left {
      flotador izquierdo;
   }
   .skin-right {
      flotar derecho;
   }
   .nav__menu li> ul {
      pantalla: ninguna! importante;
   }
   .nav__menu li: hover> ul {
      display: block! important;
      origen de transformación: centro superior;
   }
   .dropdown-menu> li {
      transición: fondo .3s;
   }
   .col-5ta-lg {
      -ms-flex: 0 0 20%;
      flexión: 0 0 20%;
      ancho máximo: 20%;
   }
}

/ * Dispositivos extra grandes * /
@media (ancho mínimo: 1200 px) {
   .col-5ta-xl {
      -ms-flex: 0 0 20%;
      flexión: 0 0 20%;
      ancho máximo: 20%;
   }
}
 
/ *]]> * / </style>

<b: comentario> Estilos de página de publicación / estática </ b: comentario>
<b: if cond = 'data: view.isSingleItem'>
<estilo> / * <! [CDATA [* /
/*Cuerpo*/
.articleTags {
    fondo acolchado: 1rem;
}
.título de la entrada {
    tamaño de fuente: 2rem;
    margen inferior: 1rem;
}
.Título de la página {
    fondo acolchado: 2rem;
    borde inferior: 2px sólido # f2f2f2;
    margen inferior: 2rem;
}
.article__cover {
    ancho: 100%;
}
.post-body {
    tamaño de fuente: 14px;
}
.article .card__header {
    margen inferior: 1.5rem;
    fondo acolchado: 0;
}
.post-related ~ .pagerPost {
    margen superior: -1rem;
}
@media (ancho mínimo: 576px) {
    .post-body {
        tamaño de fuente: 16px;
    }
}
/ * Solo artículos * /
/*Bóveda*/
.post-body h1, .post-body .h1,
.post-body h2, .post-body .h2,
.post-cuerpo h3, .post-cuerpo .h3,
.post-cuerpo h4, .post-cuerpo .h4,
.post-body h5, .post-body .h5,
.post-body h6, .post-body .h6 {
    margen: 0 0 1.5rem;
    peso de fuente: 500;
}
/*Lista*/
.post-body ul,
.post-body ol {
    margen izquierdo: 1.75em;
}
.post-body ul {
    tipo de estilo de lista: disco;
}
.post-body ul ul {
    tipo de estilo de lista: círculo;
}
.post-body ol {
    tipo de estilo de lista: decimal;
    counter-reset: contador;
}
.post-body .fa-ul {
    tipo de estilo de lista: ninguno;
}
/ * if => sin estilo * /
.post-body .list-unstyled {
  padding-left: 0;
  margen izquierdo: 0;
  estilo de lista: ninguno;
}
/*Mesa*/
.post-body table {
    alineación de texto: izquierda;
    ancho: 100%;
}
.post-body table tbody td,
.post-body table thead th {
    acolchado: 1rem;
    borde inferior: 1px sólido # e3e3e3;
    color: # 757575;
}
.post-body table thead th {
    espacio en blanco: nowrap;
    color: # 454545;
    ancho del borde: 2px;
}
/*Botón*/
.post-body .btn {
    margen derecho: 2px;
    margen inferior: 6px;
    tamaño de fuente: 1.1rem;
}
/ * si => es un fondo oscuro * /
.post-body-dark .table td,
.post-body-dark .table th {
    color: #ddd;
    color del borde: rgba (0, 0, 0, 0,75);
}
.post-body-dark .table th {
    color: #fff;
}
.post-body-dark .tab .wjs-item,
.post-body-dark .tab .wjs-item: hover {
    color: #fff;
}
/ * reacciones * /
.reactions-iframe {
    ancho: 100%;
    altura: 22px;
}
/ *]]> * / </style>
</ b: si>

<b: comentario> Opciones (¡Advertencia, puede causar fallas!) </ b: comentario>
<b: skin> <! [CDATA [
/ *!
=> Nombre del tema: Anime.xml Gratis
=> URI del tema: https://shop.zkreations.com
=> Autor: Daniel Abel M. (Copyright 2019 zkreations)
=> Autor URI: https://fb.com/danieI.abel
=> Versión: 4.3.0
=> Licencia: Creative Commons Atribucion-NoComercial 4.0 Internacional
=> URI de licencia: http://creativecommons.org/licenses/by-nc/4.0/
* /

/ * Solución: elementos innecesarios eliminados * /
.widget-item-control, .item-control.blog-admin,
.continuar, .loadmore, .thread-chrome.thread-collapsed,
.singleton-element: not (.cookie-choice s-info),
.noAllowNewComments .comentario-respuesta,
.comments .hidden {display: none}

/ * Arreglo: Mostrar caja de luz * /
.CSS_LIGHTBOX {índice z: 90001! Importante}

/ * Corrección: imágenes receptivas * /
un [estilo ^ = margen-izquierdo],
a [imageanchor]: not ([style * = float]) {
    margen derecho: 0! importante;
    margen izquierdo: 0! importante;
}

.widget-contenido img,
img [data-original-height],
img [data-original-width] {altura: auto;}

/ * Solución: videos receptivos * /
.BLOG_video_class, .b-hbp-video, .b-uploade {
    ancho máximo: 100%;
}

/ * Arreglo: Editor de comentarios * /
# comment-editor {
    borde: 0;
    ancho: 100%;
    altura mínima: 220px
}

/ * Configuraciones
   ====================
   <! - Opciones generales ->
   <Variable name = "config.comments" description = "Sistema de comentarios" type = "string" default = "blogger" value = "blogger" />
   <Variable name = "config.shortname" description = "Shortname of Disqus" type = "string" default = "shortname" value = "shortname" />
   
   <! - Animate.css ->
   <Variable name = "config.animate.search" description = "Animación del motor de búsqueda" type = "string" default = "fadeInDown .5s" value = "fadeInDown .5s" />
   <Nombre de variable = "config.animate.menu" description = "Animación de menú" type = "string" default = "flipInX .5s" value = "flipInX .5s" />
   <Variable name = "config.animate.menu.mobile" description = "Animación del menú móvil" type = "string" default = "fadeInLeft .5s" value = "fadeInLeft .5s" />
   <Nombre de variable = "config.animate.cover" description = "Animación del artículo" type = "string" default = "fadeIn .5s" value = "fadeIn .5s" />
   <Nombre de variable = "config.animate.cover.text" description = "Animación del artículo (icono)" type = "string" default = "fadeInDown .5s" value = "fadeInDown .5s" />
   
   <! - Bundle.css ->
   <Variable name = "config.bundle.ctheme" description = "Bundle comment theme" type = "string" default = "anime" value = "anime" />
   
   <! - Tarjetas (publicaciones de inicio) ->
   <Variable name = "config.post.column" description = "Número de columnas" type = "string" default = "2" value = "2" />
   <Variable name = "config.post.showSnippet" description = "Show Snippet" type = "string" default = "true" value = "true" />
   <Variable name = "config.post.showMeta" description = "Show Meta" type = "string" default = "true" value = "true" />

   <! - Relación de imagen ->
   <Variable name = "config.ratio.post" description = "Relación de aspecto" type = "string" default = "true" value = "true" />
   <Variable name = "config.ratio.slider" description = "Relación de aspecto (control deslizante)" type = "string" default = "true" value = "true" />
   <Variable name = "config.ratio.featured" description = "Relación de aspecto (publicación destacada)" type = "string" default = "true" value = "true" />
   
   <! - Mostrar ->
   <Variable name = "config.show.homeSidebar" description = "Mostrar barra lateral de inicio" type = "string" default = "true" value = "true" />
   <Variable name = "config.show.postSidebar" description = "Mostrar barra lateral de la publicación" type = "string" default = "true" value = "true" />
   <Variable name = "config.show.pageSidebar" description = "Mostrar barra lateral de la página" type = "string" default = "true" value = "true" />
   <Variable name = "config.show.errorSidebar" description = "Barra lateral en caso de error" type = "string" default = "true" value = "true" />
   <Variable name = "config.show.postPager" description = "Mostrar paginación en entradas" type = "string" default = "true" value = "true" />
   <Nombre de variable = "config.show.search" description = "Mostrar búsqueda de menú" type = "string" default = "true" value = "true" />

   <! - Funciones ->
   <Variable name = "config.el.oppositeBlog" description = "Intercambio entre la barra lateral y el blog" type = "string" default = "false" value = "false" />
   <Variable name = "config.el.postsRelated" description = "Entradas relacionadas" type = "string" default = "true" value = "true" />
   <Variable name = "config.el.postsRelated.num" description = "Número de publicaciones relacionadas" type = "string" default = "2" value = "2" />
   <Variable name = "config.el.postsRelated.column" description = "Columnas de publicaciones relacionadas" type = "string" default = "2" value = "2" />
   <Nombre de variable = "config.el.localeDate" description = "Formato de hora" type = "string" default = "en-Us" value = "en-Us" />
   <Nombre de variable = "config.el.featureTags" description = "Etiquetas de funciones" type = "string" default = "false" value = "false" />
   <Variable name = "config.el.featureTags.tags" description = "Matriz de etiquetas" type = "string" default = "" value = "" />

   <! - imagen predeterminada ->
   <Nombre de variable = "config.default.image" description = "Imagen predeterminada" type = "string" default = "https://2.bp.blogspot.com/-1J-byOnRoAI/W3Cot79qVUI/AAAAAAAADmE/IwXCcRdJl70_yR7FivfpmM62sMq16c4C no-img-blogger.png "value =" https://2.bp.blogspot.com/-1J-byOnRoAI/W3Cot79qVUI/AAAAAAAADmE/IwXCcRdJl70_yR7FivfpmM62MVqD4CwbQCLcBGAs/sg1600/
   
   <! - Mensajes predeterminados ->
   <Variable name = "config.msj.nojs" description = "Javascript Disable" type = "string" default = "Javascript required" value = "Javascript required" />
   
   Definiciones de variables
   ====================
   
   <Variable name = "keycolor" description = "Main Color" type = "color" default = "# 2196f3" value = "# 2196f3" />
   
   <Descripción del grupo = "Acentos" selector = "cuerpo">
      <Nombre de variable = "main.bg" description = "Fondo principal" type = "color" default = "# e0e0e0" value = "# e0e0e0" />
      <Variable name = "main.color" description = "Color de fondo principal" type = "color" default = "# 23a6b3" value = "# 23a6b3" />
      <Variable name = "main.linkColor" description = "Link color" type = "color" default = "# 23a6b3" value = "# 23a6b3" />
   </Grupo>
   
   <Group description = "Widths" selector = ". Main">
      <Variable name = "width.content" description = "Content width" type = "length" min = "800px" max = "1600px" default = "1240px" value = "1240px" />
      <Variable name = "width.sidebar" description = "Sidebar width" type = "length" min = "100px" max = "600px" default = "340px" value = "340px" />
      <Variable name = "width.margin" description = "Content margin" type = "length" min = "0" max = "50px" default = "30px" value = "30px" />
      <Variable name = "header.margin" description = "Separación de encabezados" type = "length" min = "0" max = "200px" default = "30px" value = "30px" />
      <Variable name = "main.margin" description = "Separación de contenido" type = "length" min = "0" max = "100px" default = "30px" value = "30px" />
   </Grupo>
   
   <Group description = "Content font" selector = "body">
      <Variable name = "font.logo" description = "Title Font" type = "font" size = "34px" family = "Custom" default = "$ (size) $ (family)" value = "$ (size) $ (familia) "/>
      <Variable name = "font.text" description = "Content font" type = "font" family = "Custom" default = "$ (family)" value = "$ (family)" />
      <Variable name = "font.desc" description = "Blog Descripción Font" type = "font" size = "14px" family = "Custom" default = "$ (size) $ (family)" value = "$ (size) $ (familia) "/>
   </Grupo>
   
   <Group description = "Content color" selector = ". Main">
      <Variable name = "body.bg" description = "Color de fondo de la página" type = "color" default = "# ffffff" value = "# ffffff" />
      <Nombre de variable = "body.colorTitle" description = "Color del título" type = "color" default = "# 262626" value = "# 262626" />
      <Variable name = "body.colorText" description = "Text Color" type = "color" default = "# 757575" value = "# 757575" />
   </Grupo>

   <Group description = "Header" selector = ". Header__wrapper">
      <Nombre de variable = "header.bg" description = "Fondo del encabezado" type = "color" default = "# f2f2f2" value = "# f2f2f2" />
      <Variable name = "header.colorLogo" description = "Color del título del blog" type = "color" default = "# 3c3c3c" value = "# 3c3c3c" />
      <Variable name = "header.colorDesc" description = "Blog Descripción Color" type = "color" default = "# 797979" value = "# 797979" />
   </Grupo>
   
   <Descripción del grupo = "Barra de encabezado" selector = ". Header__menu">
      <Variable name = "menu.bg" description = "Color de fondo" type = "color" default = "# 232323" value = "# 232323" />
      <Variable name = "menu.color" description = "Color" type = "color" default = "# ffffff" value = "# ffffff" />
   </Grupo>
   
   <Group description = "Gadgets" selector = ". Sidebar .widget">
      <Variable name = "gadget.bg" description = "Gadget Background" type = "color" default = "transparent" value = "transparent" />
      <Variable name = "gadget.title" description = "Color de fondo" type = "color" default = "# f2f2f2" value = "# f2f2f2" />
      <Variable name = "gadget.margin" description = "Separación de widgets" type = "length" min = "0" max = "50px" default = "0" value = "0" />
      <Variable name = "gadget.color" description = "Gadget Title Color" type = "color" default = "# ffffff" value = "# ffffff" />
      <Variable name = "gadget.icon" description = "Color del icono" type = "color" default = "# ffffff" value = "# ffffff" />
   </Grupo>
   
   <Descripción del grupo = "Publicaciones" selector = ". Card__content">
      <Variable name = "post.bg" description = "Color de fondo de la publicación" type = "color" default = "# f2f2f2" value = "# f2f2f2" />
      <Variable name = "post.margin" description = "Content margin" type = "length" min = "0" max = "80px" default = "28px" value = "28px" />
      <Variable name = "post.titleColor" description = "Color del título de la publicación" type = "color" default = "# 262626" value = "# 262626" />
      <Variable name = "post.dateColor" description = "Date Header Color" type = "color" default = "# 979797" value = "# 979797" />
      <Variable name = "post.borderRadius" description = "Radio del borde de la publicación" type = "length" min = "0" max = "50px" default = "0" value = "0" />
      <Variable name = "post.snippetColor" description = "Color del texto de la publicación" type = "color" default = "# 757575" value = "# 757575" />
      <Variable name = "post.share" description = "Sharing" type = "color" default = "rgba (0, 0, 0, 0.075)" value = "rgba (0, 0, 0, 0.075)" />
      <Variable name = "post.shareColor" description = "Sharing icons color" type = "color" default = "# 757575" value = "# 757575" />
   </Grupo>
   
   <Group description = "Sharing" selector = ". Footer__primary">
      <Variable name = "footer.primaryBg" description = "Color de fondo" type = "color" default = "# f2f2f2" value = "# f2f2f2" />
      <Variable name = "footer.shareColor" description = "Sharing icons color" type = "color" default = "# adadad" value = "# adadad" />
      <Variable name = "footer.linksText" description = "Text Color" type = "color" default = "# adadad" value = "# adadad" />
      <Variable name = "footer.linksColor" description = "Footer Color" type = "color" default = "# 757575" value = "# 757575" />
   </Grupo>
   
   <Group description = "Footer Links" selector = ". FooterLinks">
      <Variable name = "footer.linksBg" description = "Footer Background" type = "color" default = "# 131313" value = "# 131313" />
      <Variable name = "footer.IconColor" description = "Color del icono" type = "color" default = "# 414141" value = "# 414141" />
      <Variable name = "footer.links" description = "Link Color" type = "color" default = "# ffffff" value = "# ffffff" />
   </Grupo>

   <Variable name = "body.background" description = "Main Background" type = "background" color = "$ (main.bg)" default = "$ (color) none repetir scroll top center" value = "$ (color) ninguno repita el desplazamiento hacia el centro superior "/>
* /

body {background: $ (body.background); font-family: '$ (font.text.family)', Roboto, sans-serif} .logo__title, .skin-font, .widget-title {font-family: ' $ (font.logo.family) ', Oswald, sans-serif} .logo__descripcion {font-family:' $ (font.desc.family) ', Roboto, sans-serif} .container {max-width: $ (width .content)} @ media (min-width: 576px) {. logo__title {font-size: $ (font.logo.size)}. logo__descripcion {font-size: $ (font.desc.size)}}. drop- mayúsculas: primera letra, .pageLink.is-selected .btn, .skin-color, .skin-color-hover: hover, .tagsList__link.here, a, a: hover {color: $ (main.linkColor)}. card__overlay :: before, .dropdown-menu li> ul, .gallery__href :: before, .nav__menu a.is-currentUrl, .nav__menu> li: hover, .pageLink.is-selected .btn, .tagsList__link.here, .widget -name {background-color: $ (main.color)! important} :: - selección-moz {background-color: $ (main.color)} ::selección {background-color: $ (main.color)}. contact-form-button, .ftag-name, .skin-bg, .skin-bg-hover: hover, .widget-more-item, .wjs-item .is-active {background-color: $ (main.color)}. wjs-tab: not (.tab-vertical) .tab-header {border-bottom: 2px solid $ (main.color)}. tab-vertical .tab-header {borde derecho: 2px sólido $ (main.color)}. footer__primary, .post-body blockquote, blockquote {borde-color: $ (main.color)}. h1, .h2, .h3 ,. h4, .h5, .h6, .skin-color-title, h1, h2, h3, h4, h5, h6 {color: $ (body.colorTitle)}. skin-color-text {color: $ (body.colorText )}. header {background-color: $ (header.bg)}. search-container input {-webkit-animation: $ (config.animate.search); animation: $ (config.animate.search)}. card__image: hover .card__overlay :: before {-webkit-animation: $ (config.animate.cover); animation: $ (config.animate.cover)}. authorPortfolio, .card__readMore :: before, .portfolio-meta-content.card__title {-webkit-animation: $ (config.animate.cover.text); animation: $ (config.animate.cover.text)}. header__menu {background-color: $ (menu.bg)} @ media (max- width: 991px) {. nav__menu {background-color: $ (menu.bg); - webkit-animation: $ (config.animate.menu.mobile); animation: $ (config.animate.menu.mobile)}. nav__menu a.is-active {background-color: $ (main.color)}}. nav__toggle - intervalo de iconos, .nav__toggle - intervalo de iconos :: después, .nav__toggle - intervalo de iconos :: antes {color de fondo: $ (menu.color)}. logo__link, .logo__link: hover {color: $ (header.colorLogo)}. logo__descripcion {color: $ (header.colorDesc)} @ media (min-width: 992px) {. main {padding- top: $ (main.margin); padding-bottom: $ (main.margin)}. header__wrapper {padding-top: $ (header.margin); padding-bottom: $ (header.margin)}}. main {fondo -color: $ (body.bg)}. search-btn {color: $ (menu.color)}. nav__menu a {color: $ (menu.color)} @ media (min-width: 992px) {.nav__menu li: hover> ul {-webkit-animation: $ (config.animate.menu); animation: $ (config.animate.menu)}. blog {width: calc (100% - $ (width.sidebar) - $ (width.margin))}. sidebar {width: $ (width.sidebar)}. header .header__nav, .header__wrapper, .main {padding-left: $ (width.margin); padding-right: $ (width.margin )}. Image__full {margin-left: - $ (main.margin); margin-right: - $ (main.margin)}}. Card__content {background-color: $ (post.bg); border-radius: $ ( post.borderRadius); desbordamiento: oculto; posición: relativa} .card__title, .card__title a {color: $ (post.titleColor)}. card__item {color: $ (post.dateColor)}. card__descripcion, .post-body {color : $ (post.snippetColor)}. btn-border, .shareButtons .btn, .shareFeatured .btn {border-color: $ (post.share); color: $ (post.shareColor)} @ media (min-width: 576px) {. Card__data {padding: $ (post.margin)}. Article .card__header {margin-bottom: $ (main.margin)}. PagerPost ,.post-related, .postComments, .shareButtons: not (.card__share) {padding-top: $ (main.margin)}}. main .widget {background-color: $ (gadget.bg)}. main .widget-title {background-color: $ (gadget.title)}. main .widget-title i {color: $ (gadget.icon)}. main .widget-name, .widget-more-item, .widget-more-item: hover {color: $ (gadget.color)}. footer__primary {background: $ (footer.primaryBg)}. socialList-item {color: $ (footer.shareColor)}. footerLink .fas {color: $ (footer.IconColor) } .footerLink {color: $ (footer.links)} @ media (min-width: 992px) {. main .widget {padding: $ (gadget.margin)}. article: not (: last-child) ,. main__general .widget: last-child, .widget: not (: last-child) {margin-bottom: $ (width.margin)}. skin-box {padding: $ (width.margin)}}. footerLinks {background-color : $ (footer.linksBg)}. copy__attribution, .copy__date {color: $ (footer.linksText)}. copy__attribution a {color: $ (footer.linksColor)}postComments, .shareButtons: not (.card__share) {padding-top: $ (main.margin)}}. main .widget {background-color: $ (gadget.bg)}. main .widget-title {background-color: $ (gadget.title)}. main .widget-title i {color: $ (gadget.icon)}. main .widget-name, .widget-more-item, .widget-more-item: hover {color: $ (gadget.color)}. footer__primary {background: $ (footer.primaryBg)}. socialList-item {color: $ (footer.shareColor)}. footerLink .fas {color: $ (footer.IconColor)}. footerLink {color : $ (footer.links)} @ media (min-width: 992px) {. main .widget {padding: $ (gadget.margin)}. article: not (: last-child) ,. main__general .widget: last- child, .widget: not (: last-child) {margin-bottom: $ (width.margin)}. skin-box {padding: $ (width.margin)}}. footerLinks {background-color: $ (footer. linksBg)}. copy__attribution, .copy__date {color: $ (footer.linksText)}. copy__attribution a {color: $ (footer.linksColor)}postComments, .shareButtons: not (.card__share) {padding-top: $ (main.margin)}}. main .widget {background-color: $ (gadget.bg)}. main .widget-title {background-color: $ (gadget.title)}. main .widget-title i {color: $ (gadget.icon)}. main .widget-name, .widget-more-item, .widget-more-item: hover {color: $ (gadget.color)}. footer__primary {background: $ (footer.primaryBg)}. socialList-item {color: $ (footer.shareColor)}. footerLink .fas {color: $ (footer.IconColor)}. footerLink {color : $ (footer.links)} @ media (min-width: 992px) {. main .widget {padding: $ (gadget.margin)}. article: not (: last-child) ,. main__general .widget: last- child, .widget: not (: last-child) {margin-bottom: $ (width.margin)}. skin-box {padding: $ (width.margin)}}. footerLinks {background-color: $ (footer. linksBg)}. copy__attribution, .copy__date {color: $ (footer.linksText)}. copy__attribution a {color: $ (footer.linksColor)}card__share) {padding-top: $ (main.margin)}}. main .widget {background-color: $ (gadget.bg)}. main .widget-title {background-color: $ (gadget.title)}. main .widget-title i {color: $ (gadget.icon)}. main .widget-name, .widget-more-item, .widget-more-item: hover {color: $ (gadget.color)}. footer__primary {background: $ (footer.primaryBg)}. socialList-item {color: $ (footer.shareColor)}. footerLink .fas {color: $ (footer.IconColor)}. footerLink {color: $ (footer.links)} @media (min-width: 992px) {. main .widget {padding: $ (gadget.margin)}. article: not (: last-child) ,. main__general .widget: last-child, .widget: not (: last-child) {margin-bottom: $ (width.margin)}. skin-box {padding: $ (width.margin)}}. footerLinks {background-color: $ (footer.linksBg)}. copy__attribution, .copy__date {color: $ (footer.linksText)}. copy__attribution a {color: $ (footer.linksColor)}card__share) {padding-top: $ (main.margin)}}. main .widget {background-color: $ (gadget.bg)}. main .widget-title {background-color: $ (gadget.title)}. main .widget-title i {color: $ (gadget.icon)}. main .widget-name, .widget-more-item, .widget-more-item: hover {color: $ (gadget.color)}. footer__primary {background: $ (footer.primaryBg)}. socialList-item {color: $ (footer.shareColor)}. footerLink .fas {color: $ (footer.IconColor)}. footerLink {color: $ (footer.links)} @media (min-width: 992px) {. main .widget {padding: $ (gadget.margin)}. article: not (: last-child) ,. main__general .widget: last-child, .widget: not (: last-child) {margin-bottom: $ (width.margin)}. skin-box {padding: $ (width.margin)}}. footerLinks {background-color: $ (footer.linksBg)}. copy__attribution, .copy__date {color: $ (footer.linksText)}. copy__attribution a {color: $ (footer.linksColor)}widget {background-color: $ (gadget.bg)}. main .widget-title {background-color: $ (gadget.title)}. main .widget-title i {color: $ (gadget.icon)}. main .widget-name, .widget-more-item, .widget-more-item: hover {color: $ (gadget.color)}. footer__primary {background: $ (footer.primaryBg)}. socialList-item {color: $ (footer.shareColor)}. footerLink .fas {color: $ (footer.IconColor)}. footerLink {color: $ (footer.links)} @ media (min-width: 992px) {. main .widget {padding: $ (gadget.margin)}. article: not (: last-child) ,. main__general .widget: last-child, .widget: not (: last-child) {margin-bottom: $ (width.margin)}. skin -box {padding: $ (width.margin)}}. footerLinks {background-color: $ (footer.linksBg)}. copy__attribution, .copy__date {color: $ (footer.linksText)}. copy__attribution a {color: $ ( footer.linksColor)}widget {background-color: $ (gadget.bg)}. main .widget-title {background-color: $ (gadget.title)}. main .widget-title i {color: $ (gadget.icon)}. main .widget-name, .widget-more-item, .widget-more-item: hover {color: $ (gadget.color)}. footer__primary {background: $ (footer.primaryBg)}. socialList-item {color: $ (footer.shareColor)}. footerLink .fas {color: $ (footer.IconColor)}. footerLink {color: $ (footer.links)} @ media (min-width: 992px) {. main .widget {padding: $ (gadget.margin)}. article: not (: last-child) ,. main__general .widget: last-child, .widget: not (: last-child) {margin-bottom: $ (width.margin)}. skin -box {padding: $ (width.margin)}}. footerLinks {background-color: $ (footer.linksBg)}. copy__attribution, .copy__date {color: $ (footer.linksText)}. copy__attribution a {color: $ ( footer.linksColor)}$ (gadget.icon)}. main .widget-name, .widget-more-item, .widget-more-item: hover {color: $ (gadget.color)}. footer__primary {background: $ (footer.primaryBg) } .socialList-item {color: $ (footer.shareColor)}. footerLink .fas {color: $ (footer.IconColor)}. footerLink {color: $ (footer.links)} @ media (min-width: 992px) {.main .widget {padding: $ (gadget.margin)}. article: not (: last-child) ,. main__general .widget: last-child, .widget: not (: last-child) {margin-bottom: $ (width.margin)}. skin-box {padding: $ (width.margin)}}. footerLinks {background-color: $ (footer.linksBg)}. copy__attribution, .copy__date {color: $ (footer.linksText) } .copy__attribution a {color: $ (footer.linksColor)}$ (gadget.icon)}. main .widget-name, .widget-more-item, .widget-more-item: hover {color: $ (gadget.color)}. footer__primary {background: $ (footer.primaryBg) } .socialList-item {color: $ (footer.shareColor)}. footerLink .fas {color: $ (footer.IconColor)}. footerLink {color: $ (footer.links)} @ media (min-width: 992px) {.main .widget {padding: $ (gadget.margin)}. article: not (: last-child) ,. main__general .widget: last-child, .widget: not (: last-child) {margin-bottom: $ (width.margin)}. skin-box {padding: $ (width.margin)}}. footerLinks {background-color: $ (footer.linksBg)}. copy__attribution, .copy__date {color: $ (footer.linksText) } .copy__attribution a {color: $ (footer.linksColor)}footerLink {color: $ (footer.links)} @ media (min-width: 992px) {. main .widget {padding: $ (gadget.margin)}. article: not (: last-child) ,. main__general .widget : last-child, .widget: not (: last-child) {margin-bottom: $ (width.margin)}. skin-box {padding: $ (width.margin)}}. footerLinks {background-color: $ (footer.linksBg)}. copy__attribution, .copy__date {color: $ (footer.linksText)}. copy__attribution a {color: $ (footer.linksColor)}footerLink {color: $ (footer.links)} @ media (min-width: 992px) {. main .widget {padding: $ (gadget.margin)}. article: not (: last-child) ,. main__general .widget : last-child, .widget: not (: last-child) {margin-bottom: $ (width.margin)}. skin-box {padding: $ (width.margin)}}. footerLinks {background-color: $ (footer.linksBg)}. copy__attribution, .copy__date {color: $ (footer.linksText)}. copy__attribution a {color: $ (footer.linksColor)}
]]> </ b: piel>

<b: if cond = 'data: view.isLayoutMode'>
<b: plantilla-máscara> <! [CDATA [ 
body # layout .blog, body # layout .sidebar {width: 50%} body # layout .noSidebar {width: 100%} body # layout .skin-left {float: left} body # layout .skin-right {float: right} body # layout # three-column {width: 33.333333%; float: left} body # layout div # LinkList100 {float: left; width: 49.5%} body # layout div # Text100 {float: right; width: 49.5% } body # layout .bfix :: after {content: ""; display: table; line-height: 0; clear: both}
]]> </ b: template-skin>
</ b: si>

</head>

<body class = 'no-js'>
<script> // <! [CDATA [
document.body.classList.remove ("no-js");
//]]> </script>


<b: marcas predeterminadas>
  <b: defaultmarkup type = 'Imagen'>
    <b: includable id = 'main'>
      <b: include name = 'widget-title' />
      <b: include name = 'content' />
    </ b: includable>
    <b: includable id = 'content'>
      <div class = 'contenido-widget'>
        <b: tag class = 'imgLink' cond = 'data: link' expr: href = 'data: link' name = 'a'>
          <b: nombre de etiqueta = 'img' class = 'imgImage' expr: alt = 'data: title' expr: src = 'data: sourceUrl'>
            <b: attr cond = 'data: sourceSet' expr: value = 'data: sourceSet' name = 'srcset' />
          </ b: etiqueta>
        </ b: etiqueta>
        <b: if cond = 'data: caption'>
          <span class = 'imgCaption alert'> <data: caption /> </span>
        </ b: si>
      </div>
    </ b: includable>
  </ b: defaultmarkup>
  <b: defaultmarkup type = 'Común'>
    <b: includable id = 'título-widget'>
      <b: if cond = 'data: title.length! = 0'>
        <h3 class = 'título-widget'>
          <span class = 'nombre-widget'>
            <b: tag name = 'i' cond = 'data: icon' expr: class = 'data: icon' />
            <b: eval expr = 'data: defaultTitle?: data: title' />
          </span>
        </h3>
      </ b: si>
    </ b: includable>
    <b: includable id = 'widgetMsg'>
      <div class = 'alerta'>
        <b: eval expr = 'data: defaultMsg?: data: messages.theresNothingHere' />
      </div>
    </ b: includable>
    <b: includable id = 'pageInfo'>
      <b: if cond = 'data: view.isError'>
        <data: navMessage />
      <b: elseif cond = 'data: view.search.query o data: view.search.label' />
        <b: include data = '{defaultMsg: data: navMessage}' name = 'widgetMsg' />
      <b: elseif cond = 'data: view.isArchive' />
        <b: include data = '{defaultMsg: data: view.archive.rangeMessage}' name = 'widgetMsg' />
      <b: elseif cond = 'data: posts.empty' />
        <b: include name = 'widgetMsg' />
      </ b: si>
    </ b: includable>
    <b: includable id = 'columnClass'> <b: class cond = 'data: isColumn gte 2' name = 'col-6-sm' /> <b: class cond = 'data: isColumn gte 3' name = ' col-4-md '/> <b: class cond =' data: isColumn gte 4 'name =' col-3-lg '/> <b: class cond =' data: isColumn == 5 'name =' col -5ta-xl '/> <b: class cond =' data: isColumn == 6 'name =' col-2-xl '/> </ b: includable>
  </ b: defaultmarkup>
</ b: marcas predeterminadas>

<b: con valor = 'datos: skin.vars.config_default_image' var = 'imgDefault'>
<b: with value = '{postSidebar: data: skin.vars.config_show_postSidebar,
                homeSidebar: data: skin.vars.config_show_homeSidebar,
                pageSidebar: data: skin.vars.config_show_pageSidebar,
                errorSidebar: datos: skin.vars.config_show_errorSidebar,
                opuestoBlog: datos: skin.vars.config_el_oppositeBlog,
                showMeta: datos: skin.vars.config_post_showMeta,
                showSnippet: data: skin.vars.config_post_showSnippet,
                showShare: datos: skin.vars.config_post_showShare,
                postPager: datos: skin.vars.config_show_postPager,
                postsRelated: data: skin.vars.config_el_postsRelated,
                featureTags: data: skin.vars.config_el_featureTags,
                fTags: data: skin.vars.config_el_featureTags_tags,
                buscar: datos: skin.vars.config_show_search,
                nojsMsj: data: skin.vars.config_msj_nojs} 'var =' diseño '>

<div class = 'contenedor de caja de diseño'>
<div class = "template display-flex flex-column template-box">

<header class = "header">
<b: section id = 'header' maxwidgets = '4'>
  <b: widget id = 'Encabezado1' bloqueado = 'verdadero' título = 'Único (Cabecera)' tipo = 'Encabezado' versión = '2'>
    <b: includable id = 'main'>
      <div class = 'contenedor header__wrapper'>
        <div class = 'header__logo'>
          <b: include expr: name = 'data: image? "imagen": "título" '/>
          <b: include name = 'behindImageStyle' />
        </div>
      </div>
    </ b: includable>
    <b: includable id = 'behindImageStyle'>
      <b: include cond = 'data: image? (datos: imagePlacement == "BEFORE_DESCRIPTION"): datos: descripción 'nombre =' descripción '/>
    </ b: includable>
    <b: includable id = 'description'>
      <span class = 'logo__descripcion'> <data: description /> </span>
    </ b: includable>
    <b: includable id = 'imagen'>
      <a class='logo__image' expr:href='data:blog.homepageUrl'>
        <img expr: alt = 'data: title' expr: src = 'data: sourceUrl' />
      </a>
    </ b: includable>
    <b: includable id = 'title'>
      <b: tag class = 'logo__title' expr: name = 'data: view.isHomepage? "h1": "div" '>
        <a expr:href='data:blog.homepageUrl' class='logo__link'> <data: title /> </a>
      </ b: etiqueta>
    </ b: includable>
  </ b: widget>
  <b: ID de widget = 'HTML100' bloqueado = 'falso' título = 'Menú principal' tipo = 'HTML' versión = '2'>
    <b: configuración de widgets>
      <b: widget-setting name = 'content'> <! [CDATA [<ul class = "dropdown-menu nav__menu" id = "nav__menu">
   <li> <a href="/"> Inicio </a> </li>
   <li> <a href="#"> Comprar tema </a>
      <ul>
         <li> <a href="#"> Tienda </a>
            <ul>
               <li> <a href="#"> Gumroad </a> </li>
               <li> <a href="#"> Sitio oficial </a> </li>
            </ul>
         </li>
      </ul>
   </li>
   <li> <a href="/p/shortcodes.html"> Códigos cortos </a> </li>
</ul>]]> </ b: widget-setting>
    </ b: widgets-settings>
    <b: includable id = 'main'>
      <div class = "header__menu">
        <div class = "header__nav container flx-yc">
          <nav class = "wjs-menu skin-font">
            <button class = 'nav__toggle wjs-outsite' data-target = 'nav__menu'>
              <span class = 'nav__toggle - icon'> <span> </span> </span>
            </button>
            <datos: contenido />
          </nav>
          <b: include cond = 'data: layout.search' name = 'search' />
        </div>
      </div>
    </ b: includable>
    <b: includable id = 'buscar'>
      <button class = "search-btn flx-yc wjs-outsite skin-color-hover" data-target = "search">
        <i class = "fas fa-search"> </i>
      </button>
      <form action = "/ search" class = "nav-search flx-yc" id = "search" method = "get">
        <div class = "contenedor de búsqueda">
          <input class = "form-input" autofocus = "autofocus" autocomplete = "off" name = "q" expr: placeholder = 'data: messages.searchBlog' required = "required" spellcheck = "false" type = "text" expr: value = 'data: view.isSearch? datos: view.search.query.escaped: "" '/>
        </div>
      </form>
      <span class = "nav-search-bg stretch" />
    </ b: includable>
  </ b: widget>
</ b: sección>
</header>

<div class = "main flex-fill">
<div class = "main__blog clearfix">

<b: section id = 'general' class = 'main__general'>
  <b: widget cond = 'data: view.isHomepage' id = 'PopularPosts110' lock = 'true' title = 'Slider' type = 'PopularPosts' version = '2'>
    <b: configuración de widgets>
      <b: widget-setting name = 'numItemsToShow'> 10 </ b: widget-setting>
      <b: widget-setting name = 'showThumbnails'> verdadero </ b: widget-setting>
      <b: widget-setting name = 'showSnippets'> true </ b: widget-setting>
      <b: widget-setting name = 'timeRange'> ALL_TIME </ b: widget-setting>
    </ b: widgets-settings>
    <b: includable id = 'main'>
      <div class = 'contenido-widget'>
        <b: if cond = 'data: posts.empty'>
          <b: include name = 'widgetMsg' />
        <b: más />
          <div class = "carrusel">
            <b: include name = 'controls' />
            <div class = "carrusel__content">
              <b: valores de bucle = 'datos: publicaciones' var = 'i'>
                <div class = 'carrusel__item'>
                  <a class='gallery__href' expr:href='data:i.url'>
                    <b: include name = 'FeaturedImage' />
                    <b: include name = 'carrouselData' />
                  </a>
                </div>
              </ b: bucle>
            </div>
          </div>
        </ b: si>
      </div>
    </ b: includable>
    <b: includable id = 'carrouselData'>
      <div class = "gallery__title">
        <b: include cond = 'data: i.title.length! = 0' name = 'title' />
        <b: include name = 'Published' />
      </div>
    </ b: includable>
    <b: includable id = 'controles'>
      <button class = "carousel__controls controls__prev"> <i class = "fas fa-chevron-left fa-mn"> </i> </button>
      <button class = "carousel__controls flx-xyc controls__next"> <i class = 'fas fa-chevron-right fa-mn'> </i> </button>
    </ b: includable>
    <b: includable id = 'title'>
      <span class = 'rel__title skin-font'> <data: i.title /> </span>
    </ b: includable>
    <b: includable id = 'FeaturedImage'>
      <b: con valor = 'datos: i.featuredImage? datos: i.featuredImage: datos: imgDefault 'var =' img '>
        <img expr: src = 'data: skin.vars.config_ratio_slider? resizeImage (datos: img, 300, "300: 250"): resizeImage (datos: img, 300) 'expr: alt =' datos: i.title '/>
      </ b: con>
    </ b: includable>
    <b: includable id = 'publicado'>
        <span class = "rel__date"> <i class = 'far fa-clock' /> <data: i.date/> </span>
    </ b: includable>
    <b: includable id = 'snippet'> <! - inhabilitar -> </ b: includable>
  </ b: widget>
</ b: sección>

<b: with value = 'data: view.isMultipleItems and data: layout.homeSidebar o data: view.isPost y data: layout.postSidebar o data: view.isPage y data: layout.pageSidebar o data: view.isError y data : layout.errorSidebar o data: view.isLayoutMode 'var =' showSidebar '>

<div expr: class = '"blog" + (data: layout.oppositeBlog? "skin-right": "skin-left")'>
<b: class cond = 'data: showSidebar' name = 'showSidebar' />
<b: section id = 'Blog'>
  <b: widget id = 'Blog1' lock = 'true' title = 'Blog Posts' type = 'Blog' version = '2' visible = 'true'>
    <b: includable id = 'main'>
      <b: if cond = 'data: view.isError'>
        <b: include name = 'pageInfo' />
      <b: elseif cond = 'data: view.isMultipleItems' />
        <h3 class = 'título-widget'>
          <span class = 'nombre-widget'> <b: eval expr = 'data: view.search.query? data: view.search.query.escaped: (data: view.isLabelSearch? data: view.search.label: (data: view.isArchive? data: blog.pageName: data: messages.recentPosts)) '/> </ lapso>
        </h3>
        <b: include name = 'pageInfo' />
        <b: con valor = 'datos: skin.vars.config_post_column' var = 'isColumn'>
          <b: con valor = '{isSearch: data: view.search.query}' var = 'this'>
            <div class = "fila de elementos">
              <b: valores de bucle = 'datos: publicaciones' var = 'publicación'>
                <b: include data = 'post' name = 'post' /> <! - Incluir publicaciones ->
              </ b: bucle>
            </div>
          </ b: con>
        </ b: con>
        <b: include name = 'postPagination' /> <! - Incluir paginación ->
      <b: más />
        <b: valores de bucle = 'datos: publicaciones' var = 'publicación'>
          <article class = "artículo">
            <b: include data = 'post' name = 'post' /> <! - Incluir publicaciones ->
            <b: include data = 'post' name = 'comments' /> <! - Incluir comentarios ->
          </artículo>
        </ b: bucle>
      </ b: si>
      <b: tag async = 'async' cond = 'data: skin.vars.config_comments == "disqus" y! data: view.isError' expr: src = '+ ("//", data: skin.vars. config_shortname, ". disqus.com/count.js") 'id =' dsq-count-scr 'name =' script '/>
    </ b: includable>
    <b: includable id = 'aboutPostAuthor'> <! - deshabilitar -> </ b: includable>
    <b: includable id = 'addComments'> <! - deshabilitar -> </ b: includable>
    <b: includable id = 'comments-blogger' var = 'post'>
      <b: comentario> Paquete (Comentarios) </ b: comentario>
      <b: with value = '{dir: "//cdn.jsdelivr.net/gh/zkreations/bundle@1/dist/ctms/", theme: data: skin.vars.config_bundle_ctheme}' var = 'cmts'>
        <link expr: href = '+ (data: cmts.dir, "cmts_bundle.min.css")' rel = 'stylesheet' />
        <link expr: href = '+ (data: cmts.dir, "theme _", data: cmts.theme, ". min.css")' rel = 'stylesheet' />
      </ b: con>
      <b: include data = 'post' name = 'commentPicker' />
    </ b: includable>
    <b: includable id = 'comments-disqus' var = 'post'>
      <div id = 'disqus_thread' />
      <script>
      var disqus_shortname = "<data: skin.vars.config_shortname />",
          disqus_config = function () {
             this.page.url = "<data: view.url.canonical />";
             this.page.title = "<data: view.title.escaped />";
          }; // <! [CDATA [
       (función () {
           var d = documento, s = d.createElement ('script');
           s.async = true; s.src = '//' + disqus_shortname + '.disqus.com / embed.js';
           s.setAttribute ('data-timestamp', + nueva fecha ()); (d.head || d.body) .appendChild (s);
       }) (); //]]>
       </script>
    </ b: includable>
    <b: includable id = 'comments-facebook' var = 'post'>
      <div class = 'fb-comments' data-colorscheme = 'light' data-numposts = '10 'data-width =' 100% 'expr: data-href =' data: view.url.canonical '/>
    </ b: includable>
    <b: includable id = 'commentAuthorAvatar'> <! - deshabilitar -> </ b: includable>
    <b: includable id = 'commentDeleteIcon' var = 'comment'> <! - deshabilitar -> </ b: includable>
    <b: includable id = 'commentForm' var = 'post'> <! - deshabilitar -> </ b: includable>
    <b: includable id = 'commentFormIframeSrc' var = 'post'> <! - deshabilitar -> </ b: includable>
    <b: includable id = 'commentItem' var = 'comment'> <! - deshabilitar -> </ b: includable>
    <b: includable id = 'commentList' var = 'comments'> <! - deshabilitar -> </ b: includable>
    <b: includable id = 'commentPicker' var = 'post'>
      <div class = 'comments' id = 'comments'>
         <b: class cond = '! data: post.allowNewComments' name = 'noAllowNewComments' />
         <div class = 'comentarios-contenido'>
            <div id = 'comment-holder'> <data: post.commentHtml /> </div>
            <b: include data = 'post' name = 'threaddedCommentJs' />
         </div>
         <b: include data = 'post' expr: name = 'data: post.allowNewComments? "threaddedCommentForm": "mensaje de estado" '/>
      </div> 
    </ b: includable>
    <b: includable id = 'comments' var = 'post'>
      <b: if cond = 'data: post.allowComments'>
        <div class = 'postComments'>
        <h3 class = 'título-widget'>
          <span class = 'nombre-widget'>
            <b: if cond = 'data: skin.vars.config_comments! = "blogger"'>
              <datos: skin.vars.config_comments />
            <b: más />
              <b: nombre del mensaje = 'messages.numberOfComments'>
                <b: param expr: value = 'data: post.numberOfComments' name = 'numComments' />
              </ b: mensaje>
            </ b: si>
          </span>
        </h3>
        <b: include data = 'post' expr: name = 'data: view.isPreview? "mensaje-estado": "comentarios-" + datos: skin.vars.config_comments '/>
        </div>
      </ b: si>
    </ b: includable>
    <b: includable id = 'commentsTitle'> <! - deshabilitar -> </ b: includable>
    <b: includable id = 'feedLinks'> <! - deshabilitar -> </ b: includable>
    <b: includable id = 'feedLinksBody' var = 'links'> <! - deshabilitar -> </ b: includable>
    <b: includable id = 'homePageLink'> <! - deshabilitar -> </ b: includable>
    <b: includable id = 'iframeComments' var = 'post'> <! - deshabilitar -> </ b: includable>
    <b: includable id = 'inlineAd'> <! - deshabilitar -> </ b: includable>
    <b: includable id = 'nextPageLink'>
      <a class='btn btn-border' expr:href='data:olderPageUrl'>
        <b: class cond = 'data: view.isPost' name = 'post-pageUrl' />
        <b: eval expr = 'datos: view.isPost? data: messages.olderPosts: data: messages.older '/> <i class =' ​​fas fa-arrow-right '/>
      </a>
    </ b: includable>
    <b: includable id = 'post' var = 'post'>
    
      <b: if cond = 'data: this.isSearch'>

        <! - {{Página de búsqueda}} ->
        <b: include name = 'postCardSearch' />

      <b: elseif cond = 'data: view.isMultipleItems' />

        <! - {{Página de inicio}} ->
        <b: include name = 'postCard' />

      <b: elseif cond = 'data: view.isPost' />

        <! - {{Publicaciones}} ->
        <b: include name = 'postHeader' />
        <b: include name = 'postBody' />
        <b: include name = 'postFooter' />

      <b: elseif cond = 'data: view.isPage' />

        <! - {{Página estática}} ->
        <b: include name = 'postHeader' />
        <b: include name = 'postBody' />

      </ b: si>

    </ b: includable>
    <b: includable id = 'postBody'>
      <div class = 'post-body clearfix skin-color-text' expr: id = 'data: post.id'>
        <data: post.body />
      </div>
    </ b: includable>
    <b: includable id = 'postBodySnippet'>
      <b: if cond = 'data: post.snippets'>
        <p class = "card__descripcion"> <b: eval expr = '! data: length? data: post.snippets.short: (data: post.snippets.long snippet {length: data: length}) '/> </p>
      </ b: si>
    </ b: includable>
    <b: includable id = 'postCard'>
      <div class = 'tarjeta col-12'>
        <b: include name = 'columnClass' />
        <div class = "card__content">
          <b: con valor = 'datos: layout.fTags' var = 'etiquetas'>
            <b: include cond = 'data: layout.featureTags' name = 'postFeaturedTags' />
          </ b: con>
          <b: include name = 'postFeaturedImage' />
          <div class = "card__data">
            <b: include name = 'postHeader' />
            <b: include cond = 'data: layout.showSnippet' name = 'postBodySnippet' data = '{length: 100}' />
            <b: include cond = 'data: layout.showMeta' name = 'postMeta' />
          </div>
        </div>
      </div>
    </ b: includable>
    <b: includable id = 'postCardSearch'>
      <div class = 'card col-12 card-search'>
        <div class = 'card__content'>
          <div class = 'card__data'>
            <b: con valor = 'datos: post.featuredImage? data: post.featuredImage: data: imgDefault 'var =' img '>
              <img class = 'search-img' expr: alt = 'data: post.title' expr: src = 'resizeImage (data: img, 50, "1: 1")' />
            </ b: con>
            <div class = 'datos de búsqueda'>
              <b: include name = 'postHeader' />
              <b: include name = 'postBodySnippet' data = '{length: 120}' />
            </div>
          </div>
        </div>
      </div>
    </ b: includable>
    <b: includable id = 'postCommentsAndAd' var = 'post'> <! - deshabilitar -> </ b: includable>
    <b: includable id = 'postCommentsLink'>
      <a class='card__item' expr:href='data:post.url fragment "comments"'>
        <i class = 'far fa-comment' />
        <b: if cond = 'data: skin.vars.config_comments == "disqus"'>
          <span class = 'disqus-comment-count' expr: data-disqus-url = 'data: post.url.canonical' />
        <b: elseif cond = 'data: skin.vars.config_comments == "facebook"' />
          <span class = 'fb-comments-count' expr: data-href = 'data: post.url.canonical' />
        <b: más />
          <data: post.numberOfComments />
        </ b: si>
      </a>
    </ b: includable>
    <b: includable id = 'postFeaturedImage'>
      <b: nombre de etiqueta = 'a' cond = 'data: view.isMultipleItems' class = 'card__image flex-none' expr: href = 'data: post.url'>
        <span class = 'card__overlay' />
        <i class = 'card__readMore flx-xyc fas fa-search' />
        <b: con valor = 'datos: post.featuredImage? data: post.featuredImage: data: imgDefault 'var =' img '>
          <b: with value = '{big: (data: skin.vars.config_ratio_post? resizeImage (data: img, 900, "16: 9"): resizeImage (data: img, 900)), medio: (data: skin .vars.config_ratio_post? resizeImage (data: img, 500, "1: 1"): resizeImage (data: img, 500)), pequeña: (data: skin.vars.config_ratio_post? resizeImage (data: img, 380, " 16: 9 "): resizeImage (data: img, 300))} 'var =' imgSize '>
            <img expr: alt = 'data: post.title' expr: src = 'data: imgSize.small' />
          </ b: con>
        </ b: con>
      </ b: etiqueta>
    </ b: includable>
    <b: includable id = 'postFeaturedTags'>
      <b: if cond = '! data: tags'>
        <div class = 'ftag-content'>
          <a expr:class='"ftag-name ftag-" + data:post.labels.first.name' expr:href='data:post.labels.first.url'>
            <i class = 'fas fa-tag' /> <data: post.labels.first.name/>
          </a>
        </div>
      <b: elseif cond = 'data: post.labels any (t => t.name in data: tags)' />
        <div class = 'ftag-content'>
        <b: loop values ​​= 'data: post.labels filter (t => t.name en data: tags)' var = 'i'>
          <a expr:class='"ftag-name ftag-" + data:i.name' expr:href='data:i.url'> <i class = 'fas fa-tag' /> <data: i. nombre /> </a>
        </ b: bucle>
        </div>
      </ b: si>
    </ b: includable>
    <b: includable id = 'postFooter'>
      <b: include name = 'postShare' />
      <b: include cond = 'data: layout.postsRelated' name = 'postRelated' />
      <b: include cond = 'data: layout.postPager' name = 'postPagination' />
    </ b: includable>
    <b: includable id = 'postFooterAuthorProfile'>
      <b: if cond = 'data: widgets.Blog.first.allBylineItems.author'>
        <b: con valor = 'datos: post.author.authorPhoto? datos: post.author.authorPhoto.image: "https://2.bp.blogspot.com/-hroWP5PDx-w/XT3h2s0xMLI/AAAAAAAAEDk/iBbeT96r5ZoEQed1DbkL-oZd1oGBGokRg1cBGAs/support ' >
          <a class='card__item' expr:href='data:post.author.profileUrl' rel='author' target='_blank'>
            <img class = 'card__authorImage' expr: alt = 'data: post.author.name' expr: src = 'resizeImage (data: imgAuthor, 30, "1: 1")' />
            <span class = "card__authorName skin-color-title skin-color-hover"> <data: post.author.name/> </span>
          </a>
        </ b: con>
      </ b: si>
    </ b: includable>
    <b: includable id = 'postHeader'>
      <header class = "card__header">
        <b: include cond = 'data: view.isPost' name = 'postLabels' />
        <b: include name = 'postTitle' />
        <b: include cond = 'data: view.isPost' name = 'postMeta' />
      </header>
    </ b: includable>
    <b: includable id = 'postJumpLink' var = 'post'> <! - deshabilitar -> </ b: includable>
    <b: includable id = 'postMeta'>
      <div class = "card__meta">
        <b: include name = 'postFooterAuthorProfile' />
        <b: include cond = 'data: widgets.Blog.first.allBylineItems.timestamp' name = 'postTimestamp' />
        <b: include cond = 'data: widgets.Blog.first.allBylineItems.comments' name = 'postCommentsLink' />
      </div>
    </ b: includable>
    <b: includable id = 'postLabels'>
      <b: if cond = 'data: post.labels.any y data: post.labels'>
        <div class = 'articleTags display-flex flex-wrap'>
          <b: valores de bucle = 'datos: post.labels' var = 'i'>
            <a class='btn btn-border' expr:href='data:i.url' rel='tag'> <data: i.name/> </a>
          </ b: bucle>
        </div>
      </ b: si>
    </ b: includable>
    <b: includable id = 'postPagination'>
      <b: tag cond = 'data: newerPageUrl o data: previousPageUrl' expr: class = 'data: view.isPost? "pagerPost display-flex justify-content-between": "blog-pager" 'id =' blog-pager 'name =' div '>
        <b: include cond = 'data: newerPageUrl' name = 'previousPageLink' />
        <b: include cond = 'data: previousPageUrl' name = 'nextPageLink' />
      </ b: etiqueta>
    </ b: includable>
    <b: includable data = 'post' id = 'postRelated'>
      <b: if cond = '! data: blog.isPrivateBlog y data: post.labels'>
      <div class = 'relacionado con la publicación'>
        <h3 class = 'título-widget'>
          <span class = 'nombre-widget'> <data: messages.youMayLikeThesePosts /> </span>
        </h3>
        <div id = 'wjs-related' class = 'fila de elementos relacionados con wjs' />
      </div>
      <script>
      / *!
       * v2.1.0 relacionado con wjs
       * Copyright 2019 zkreations
       * Desarrollado por José Gregorio (fb.com/JGMateran)
       * Con licencia de MIT (github.com/zkreations/wjs-related/blob/master/LICENSE)
       * /
       var related = (function () {
       'uso estricto';
       var por defecto = {
         id: '<data: post.id/>',
         página de inicio: window.location.protocol + '//' + window.location.hostname,
         imagen: '<b: eval expr =' resizeImage (datos: imgDefault, 400) '/>',
         longitud: <data: skin.vars.config_el_postsRelated_num />,
         localeDate: '<datos: skin.vars.config_el_localeDate />',
         fragmento: 80,
         imgSize: 'w300-h200-c',
         contenedor: document.getElementById ('relacionado con wjs'),
         etiquetas: [<b: loop values ​​= 'data: post.labels' var = 'label'> '<data: label.name />', </ b: loop>]
       };
       // <! [CDATA [
       var etiquetas $ length = defaults.tags.length;
       var script = document.createElement ('script');
       var src = defaults.homepage + '/ feeds / posts / default' +
          '? alt = json-en-script' +
          '& callback = relacionado' +
          '& max-results =' + (defaults.length + 1) +
          '& q =';
       para (var n = 0; n <etiquetas $ longitud; n ++) {
          src + = 'etiqueta: "' + defaults.tags [n] + '"' + (n === etiquetas $ longitud - 1? '': '|');
       }
       
       script.src = src;
       
       document.body.appendChild (script);
       
       función render (datos) {
          var title = data.title. $ t;
          var content = data.content;
          var resumen = data.summary;
          var body = content? contenido. $ t: resumen. $ t;
          var snippet = (body) .replace (/ <[^>] *>? / g, ''). substring (0, defaults.snippet) + '...';
          var img = data.media $ miniatura;
          var tempHtml = document.createElement ('div');
          tempHtml.innerHTML = cuerpo;
          var imgHtml = tempHtml.querySelector ('img');
          var image = (img? img.url: (imgHtml? imgHtml.src: defaults.image)). replace (/ [swh] \ d {2,4} (?: - [swh] \ d {2,4} )? (?: - c)? /, defaults.imgSize);
          var url = (función () {
             para (var i = 0; i <data.link.length; i ++) {
                var link = data.link [i];
                if (link.rel === 'alternativo') {
                   return link.href;
                }
             }
          }) ();
          var publicado = nueva fecha (datos.publicado. $ t) .toLocaleDateString (
             defaults.localeDate,
             {
                año: 'numérico',
                mes: 'largo',
                día: 'numérico'
             }
          ); //]]>
          return (<b: con valor = 'datos: skin.vars.config_el_postsRelated_column' var = 'isColumn'>
             "<div class = 'gallery col-12'> <b: include name = 'columnClass' />" +
                 "<a href='" + url + "'class='gallery__href'>" +
                    "<img class = 'gallery__image' src = '" + imagen + "' />" +
                    "<div class = 'gallery__title'>" +
                      "<span class = 'rel__title skin-font'>" + título + "</span>" +
                      "<time class = 'rel__date'> <i class = 'far fa-clock'> </i>" + publicado + "</time>" +
                    "</div>" +
                 "</a>" +
             "</div>"
          ); </ b: con> // <! [CDATA [
       }
       función relacionada (json) {
          var i = 0;
          var post;
          var length = defaults.length;
          for (; i <length && (post = json.feed.entry [i]); i ++) {
             if (defaults.id! == post.id. $ t.split ('.post-') [1]) {
                defaults.container.innerHTML + = render (publicar);
             } demás {
                longitud ++;
             }
          }
       }
       retorno relacionado;
       //]]>
       }) (); </script>
      </ b: si>
    </ b: includable>
    <b: includable id = 'postShare'>
      <b: if cond = 'data: post.shareUrl'>
        <div class = "shareButtons display-flex flex-wrap">
          <a class='btn btn-border wjs-window' expr:href='params(data:post.shareUrl,{target: "facebook"})'> <i class = 'fab fa-facebook-f fa-mn fa-fw '/> </a>
          <a class='btn btn-border wjs-window' expr:href='params(data:post.shareUrl,{target: "twitter"})'> <i class = 'fab fa-twitter fa-mn fa- fw '/> </a>
          <a class='btn btn-border wjs-window' expr:href='params(data:post.shareUrl,{target: "pinterest"})'> <i class = 'fab fa-pinterest-p fa-mn fa-fw '/> </a>
          <a class = 'btn btn-border wjs-window' expr: href = 'params ("// www.tumblr.com/widgets/share/tool/preview",{canonicalUrl: data: post.url.canonical, caption : data: post.snippets.short, posttype: "link", title: data: post.title}) '> <i class =' ​​fab fa-tumblr fa-mn fa-fw '/> </a>
          <b: if cond = 'data: post.emailPostUrl'>
            <a class='btn btn-border wjs-window' expr:href='params(data:post.shareUrl,{target: "email"})'> <i class = 'fas fa-at fa-mn fa- fw '/> </a>
          </ b: si>
        </div>
      </ b: si>
    </ b: includable>
    <b: includable id = 'postTitle'>
      <b: if cond = 'data: post.title.length! = 0'>
        <b: tag class = 'card__title skin-font' expr: name = 'data: view.isMultipleItems? "h2": "h1" '>
          <b: class cond = 'data: view.isSingleItem' name = 'post__title' />
          <b: class cond = 'data: view.isPage' name = 'page__title' />
          <b: tag class = 'skin-color-hover' cond = 'data: view.isMultipleItems' expr: href = 'data: post.url' name = 'a'>
            <datos: post.title />
          </ b: etiqueta>
        </ b: etiqueta>
      </ b: si>
    </ b: includable>
    <b: includable id = 'postTimestamp'>
      <time class = 'card__item' expr: datetime = 'data: post.date.iso8601'> <i class = 'far fa-clock' /> <data: post.date/> </time>
    </ b: includable>
    <b: includable id = 'previousPageLink'>
      <a class='btn btn-border' expr:href='data:newerPageUrl'>
        <b: class cond = 'data: view.isPost' name = 'post-pageUrl' />
        <i class = 'fas fa-arrow-left' /> <b: eval expr = 'data: view.isPost? data: messages.newerPosts: data: messages.newer '/>
      </a>
    </ b: includable>
    <b: includable id = 'threaddedCommentForm' var = 'post'>
      <div class = 'formulario de comentario'>
         <a expr:href='data:post.commentFormIframeSrc' id='comment-editor-src'/>
         <iframe class = 'blogger-iframe-colorear blogger-comment-from-post' id = 'comment-editor' src = '' />
         <datos: post.cmtfpIframe />
         <script> BLOG_CMT_createIframe ("<datos: post.appRpcRelayPath />"); </script>
      </div>
    </ b: includable>
    <b: includable id = 'mensaje de estado'>
      <div class = 'alerta'>
        <b: eval expr = 'data: view.isPreview? data: messages.widgetNotAvailableInPreview: data: post.noNewCommentsText '/>
      </div>
    </ b: includable>
    <b: includable id = 'threaddedCommentJs' var = 'post'>
      <script async = 'async' expr: src = 'data: post.commentSrc' />
      <b: template-script inline = 'true' name = 'thread_comments' />
      <b: if cond = 'data: post.showThreadedComments'>
         <script> blogger.widgets.blog.initThreadedComments (
            <data: post.commentJso />,
            <data: post.commentMsgs />,
            <data: post.commentConfig />); // <! [CDATA [
            var a = document.getElementsByClassName ("contenedor-imagen-avatar");
            para (i = 0; i <a.length; i ++) a [i] .childNodes [0] .setAttribute ("src", a [i] .childNodes [0] .getAttribute ("src"). reemplazar (/ s \ B \ d {2,4} /, "s80"));
         //]]> </script>
      </ b: si>
    </ b: includable>
    <b: includable id = 'threaddedComments' var = 'post'> <! - deshabilitar -> </ b: includable>
  </ b: widget>
  <b: widget cond = 'data: view.isHomepage' id = 'LinkList210' lock = 'true' title = 'WJS Sections' type = 'LinkList' version = '2' visible = 'true'>
    <b: includable id = 'main'>
      <div class = 'secciones'>
      <b: valores de bucle = 'datos: enlaces' var = 'sección'>
        <b: with expr: value = '"{" + data: section.target + "}"' var = 'category'>
          <div class = 'widget'>
            <b: include name = 'section-title' />
            <b: include name = 'content' />
          </div>
        </ b: con>
      </ b: bucle>
      </div>
      <b: include name = 'js' />
    </ b: includable>
    <b: includable id = 'sección-título'>
      <h3 class = 'título-widget'>
        <span class = 'widget-name'> <data: section.name/> </span>
        <a class='widget-more widget-more-item flx-xyc' expr:href='+("/search/label/",data:category.tag)' rel='nofollow'>
          <datos: messages.showAll />
        </a>
      </h3>
    </ b: includable>
    <b: includable id = 'content' data = 'category'>
      <div class = 'contenido-widget'>
        <div class = "wjs-section items row" expr: data-category = "data: category.tag">
          <b: attr cond = 'data: category.results' name = 'data-max-results' expr: value = 'data: category.results' />
          <svg xmlns = "http://www.w3.org/2000/svg" class = 'circular'> <circle r = '9.6px' cx = '24px' cy = '24px' class = 'path' /> </svg>
        </div>
        <noscript> <p class = 'alert'> <data: layout.nojsMsj /> </p> </noscript>
      </div>
    </ b: includable>
    <b: includable id = 'js'>
      <script>
        / *!
         * wjs-section v2.1.0
         * Copyright 2019 zkreations
         * Desarrollado por José Gregorio (fb.com/JGMateran)
         * Con licencia de MIT (github.com/zkreations/wjs-sections/blob/master/LICENSE)
         * /
        'uso estricto';
        var devoluciones de llamada = {};
        var por defecto = {
            homeUrl: window.location.protocol + "//" + window.location.hostname,
            imagen: '<b: eval expr =' resizeImage (datos: imgDefault, 400) '/>',
            className: '.wjs-section',
            imgSize: 'w380-h213-pk-no-nu', // Tamaño de imagen (parametros de picasa)
            snippet: 100, // Cantidad texto para el resumen,
            locale: '<datos: skin.vars.config_el_localeDate />'
        };
        var datas = {expReg: / [swh] \ d {2,4} (?: - [swh] \ d {2,4})? (?: - c)? /, category: null, "max-results ": 6, plantilla: {<b: con valor = 'datos: skin.vars.config_post_column' var = 'isColumn'>
        "default": "<div class = 'card card-grid col-12'> <b: include name = 'columnClass' /> <div class = 'card__content'> <b: if cond = 'data: layout.featureTags '> <div class =' ​​ftag-content '> <a class='ftag-name ftag-TAG_NAME' href='TAG_URL'> <i class =' ​​fas fa-tag '> </i> TAG_NAME </a> </div> </ b: if> <a class='card__image flex-none' href='URL'> <span class = 'card__overlay'> </span> <i class = 'card__readMore flx-xyc fas fa- buscar '> </i> <img src =' IMG_DEFAULT '/> </a> <div class =' ​​card__data '> <header class =' ​​card__header '> <h2 class =' ​​card__title skin-font '> <una clase = 'skin-color-hover' href = 'URL'>TITLE </a> </h2> </header> <b: if cond = 'data: layout.showSnippet'> <p class = 'card__descripcion'> SNIPPET </p> </ b: if> <b: if cond = 'data: layout.showMeta'> <div class = 'card__meta'> <b: if cond = 'data: widgets.Blog.first.allBylineItems.author'> <a class = 'card__item' href = 'AUTHOR_URL' rel = 'author' target = '_ blank'> <img class = 'card__authorImage' src = 'AUTHOR_IMAGE' /> <span class = 'card__authorName skin-color-title skin-color-hover'> AUTHOR_NAME </span> </ a> </ b: if> <b: if cond = 'data: widgets.Blog.first.allBylineItems.timestamp'> <time class = 'card__item'> <i class = 'far fa-clock'> </ i > HORA </time> </ b: if> </div> </ b: if> </ div> </div> </div> ", </ b: con> // <! [CDATA [
        vacío: '<div class = "col-12"> <p class = "alert"> No se han encontrado entradas </p> </div>'}}; función paraCada (d, b) {var a, c ; para (a = 0; (c = d [a ++]) &&! 1! == b.call (c, a, c);); return d}
        function getCurrentData (d) {var b, a, c = {}; for (b en datas) (a = d.getAttribute ("data -" + b)) && (c [b] = a); return c} function temp (d, b) {for (var a in b) d = d.replace (new RegExp (a, "g"), b [a]); return d}
        function getLabel (d, b) {var a, c = b.category, g = document.createElement ("script"), h = defaults.homeUrl + "/ feeds / posts / default? alt = json-in-script & callback = callbacks . "+ c.replace (/ [^ A-Z0-9] / ig, ''); devoluciones de llamada [c.replace (/ [^ A-Z0-9] / ig, '')] = función (a) {var c, l = "", g = a.feed.entry; if (g) para (a = 0; c = g [a ++];) {var k = c.content, e = c.summary; k = k? k. $ t: e. $ t; e = c.media $ miniatura; var f = document.createElement ("div"); f.innerHTML = k; var h = f.querySelector ("img") ; f = c.author [0]; e = e? e.url: h? h.src: defaults.image; l + = temp (b.template, {TAG_NAME: b.category, TAG_URL: defaults.homeUrl + "/ search / label / "+ b.category, AUTHOR_NAME: f.name. $ t, AUTHOR_URL: f.uri? f.uri. $ t: '# noAuthor', AUTHOR_IMAGE: f.gd $ image.src.replace (/ s \ B \ d {2,4} /,
        "w30-h30-pk-no-nu"), IMG_DEFAULT: e.replace (datas.expReg, defaults.imgSize), TITLE: c.title. $ t, TIME: (nueva fecha (c.published. $ t) ) .toLocaleDateString (defaults.locale, {month: "long", day: "2-digit"}), SNIPPET: k.replace (/ <[^>] *>? / g, ""). substring (0 , defaults.snippet) + "...", URL: function () {var a, b; for (a = 0; b = c.link [a ++];) if ("alternate" === b.rel ) return b.href}})} más l + =
        datas.template.empty; d.innerHTML = l}; for (a in b) "template"! == a && (h + = "&" + a + "=" + b [a]); g.src = h; document.body.appendChild (g)} forEach (document.querySelectorAll (defaults.className), function (d, b) {var a = getCurrentData (b); a.category && (a ["max-results"] || ( a ["max-results"] = datas ["max-results"]), a.template = datas.template ["predeterminado"], getLabel (b, a))});
      //]]> </script>
    </ b: includable>
  </ b: widget>
</ b: sección>
</div>

<b: if cond = 'data: showSidebar'>
<div expr: class = '"sidebar" + (data: layout.oppositeBlog? "skin-left": "skin-right")'>
<b: section id = 'sidebar'>
  <b: widget id = 'BlogSearch1' bloqueado = 'falso' título = 'Buscar' tipo = 'BlogSearch' visible = 'true'>
    <b: includable id = 'main'>
      <b: include name = 'widget-title' />
      <b: include name = 'content' />
    </ b: includable>
    <b: includable id = 'content'>
      <div class = 'contenido-widget'>
        <b: include name = 'searchForm' />
      </div>
    </ b: includable>
    <b: includable id = 'searchForm'>
      <form class = 'searchForm display-flex' expr: action = 'data: blog.searchUrl' method = 'get'>
        <b: attr cond = 'no datos: view.isPreview' name = 'target' value = '_ top' />
        <input autocomplete = 'off' class = 'searchForm__input form-input' expr: placeholder = 'data: messages.searchBlog' expr: value = 'data: view.isSearch? data: view.search.query.escaped: "" 'name =' q 'required =' required 'spellcheck =' false 'type =' text '/>
        <b: include name = 'searchSubmit' />
      </form>
    </ b: includable>
    <b: includable id = 'searchSubmit'>
      <button class = 'searchForm__button btn skin-bg' type = 'submit'> <i class = 'fas fa-search fa-fw fa-mn skin-i' /> </button>
    </ b: includable>
  </ b: widget>
  <b: widget id = 'FeaturedPost1' bloqueado = 'false' title = 'Publicación destacada' tipo = 'FeaturedPost' visible = 'true'>
    <b: configuración de widgets>
      <b: widget-setting name = 'showSnippet'> true </ b: widget-setting>
      <b: widget-setting name = 'showPostTitle'> true </ b: widget-setting>
      <b: widget-setting name = 'showFirstImage'> true </ b: widget-setting>
      <b: widget-setting name = 'useMostRecentPost'> true </ b: widget-setting>
    </ b: widgets-settings>
    <b: includable id = 'main' var = 'this'>
      <b: include name = 'widget-title' />
      <b: include name = 'content' />
    </ b: includable>
    <b: includable id = 'content'>
      <div class = 'contenido-widget'>
        <div class = 'FeaturedPost card__content'>
          <b: valores de bucle = 'datos: publicaciones' var = 'publicación'>
            <b: include cond = 'data: postDisplay.showFeaturedImage' name = 'postFeaturedImage' />
            <div class = 'FeaturedPost-data card__data'>
              <b: include cond = 'data: postDisplay.showTitle' name = 'postTitle' />
              <b: include cond = 'data: postDisplay.showSnippet' name = 'postBodySnippet' />
              <b: include cond = 'data: post.shareUrl' name = 'postShare' />
            </div>
          </ b: bucle>
        </div>
      </div>
    </ b: includable>
    <b: includable id = 'postBodySnippet'>
      <p class = 'card__descripcion'> <b: eval expr = 'data: post.snippets.long snippet {length: 100}' /> </p>
    </ b: includable>
    <b: includable id = 'postFeaturedImage'>
      <a class='card__image flex-none' expr:href='data:post.url'>
        <i class = 'card__icon skin-bg fas fa-star fa-mn skin-i' />
        <b: con valor = 'datos: post.featuredImage? data: post.featuredImage: data: imgDefault 'var =' img '>
          <b: con valor = 'datos: skin.vars.config_ratio_featured? resizeImage (datos: img, 300, "16: 9"): resizeImage (datos: img, 300) 'var =' imgPost '>
            <img expr: alt = 'data: post.title' expr: src = 'data: imgPost' />
          </ b: con>
        </ b: con>
      </a>
    </ b: includable>
    <b: includable id = 'postShare'>
      <div class = 'shareFeatured flx-xyc flex-wrap'>
        <a class='btn btn-border wjs-window' expr:href='params(data:post.shareUrl,{target: "facebook"})'> <i class = 'fab fa-facebook-f fa-mn fa-fw '/> </a>
        <a class='btn btn-border wjs-window' expr:href='params(data:post.shareUrl,{target: "twitter"})'> <i class = 'fab fa-twitter fa-mn fa- fw '/> </a>
        <a class='btn btn-border wjs-window' expr:href='params(data:post.shareUrl,{target: "pinterest"})'> <i class = 'fab fa-pinterest-p fa-mn fa-fw '/> </a>
        <b: if cond = 'data: post.emailPostUrl'>
          <a class='btn btn-border wjs-window' expr:href='params(data:post.shareUrl,{target: "email"})'> <i class = 'fas fa-at fa-mn fa- fw '/> </a>
        </ b: si>
      </div>
    </ b: includable>
    <b: includable id = 'postTitle'>
      <b: if cond = 'data: post.title.length! = 0'>
        <h4 class = 'card__title skin-font'>
          <a class='skin-color-hover' expr:href='data:post.url'> <data: post.title /> </a>
        </h4>
      </ b: si>
    </ b: includable>
  </ b: widget>
  <b: widget id = 'Label100' bloqueado = 'falso' título = 'Etiquetas' tipo = 'Etiqueta' versión = '2'>
    <b: configuración de widgets>
      <b: widget-setting name = 'display'> NUBE </ b: widget-setting>
    </ b: widgets-settings>
    <b: includable id = 'main'>
      <b: include name = 'widget-title' />
      <b: include name = 'content' />
    </ b: includable>
    <b: includable id = 'nube'>
      <div class = 'tagsList display-flex align-items-start flex-wrap'>
        <b: class cond = 'data: display == "list"' name = 'tagsList - list' />
        <b: valores de bucle = 'datos: etiquetas' var = 'i'>
          <b: include name = 'list' />
        </ b: bucle>
      </div>
    </ b: includable>
    <b: includable id = 'content'>
      <div class = 'contenido-widget'>
        <b: include name = 'cloud' />
      </div>
    </ b: includable>
    <b: includable id = 'lista'>
      <a class='tagsList__link btn' expr:href='data:i.url'>
        <b: class cond = 'data: view.url == data: i.url' name = 'here' /> <data: i.name/>
        <b: include cond = 'data: showFreqNumbers' name = 'numbers' />
      </a>
    </ b: includable>
    <b: includable id = 'números'>
      <span class = 'tags-list__num'> <data: i.count /> </span>
    </ b: includable>
  </ b: widget>
  <b: widget id = 'PopularPosts100' bloqueado = 'false' title = 'Publicaciones populares' tipo = 'PopularPosts' versión = '2'>
    <b: configuración de widgets>
      <b: widget-setting name = 'numItemsToShow'> 4 </ b: widget-setting>
      <b: widget-setting name = 'showThumbnails'> verdadero </ b: widget-setting>
      <b: widget-setting name = 'showSnippets'> true </ b: widget-setting>
      <b: widget-setting name = 'timeRange'> ALL_TIME </ b: widget-setting>
    </ b: widgets-settings>
    <b: includable id = 'main'>
      <b: include name = 'widget-title' />
      <div class = 'contenido-widget'>
        <b: if cond = 'data: posts.empty'>
          <b: include name = 'widgetMsg' />
        <b: más />
          <b: valores de bucle = 'datos: publicaciones' var = 'i'>
            <div class = 'hotPosts__content display-flex align-items-start'>
              <b: include cond = 'data: postDisplay.showFeaturedImage' name = 'FeaturedImage' />
              <div class = 'hotPosts__data'>
                <b: include name = 'title' />
                <b: include cond = 'data: postDisplay.showSnippet' name = 'snippet' />
              </div>
            </div>
          </ b: bucle>
        </ b: si>
      </div>
    </ b: includable>
    <b: includable id = 'title'>
      <h2 class = 'hotPosts__title'> <a class='skin-color-hover' expr:href='data:i.url'> <data: i.title /> </a> </h2>
    </ b: includable>
    <b: includable id = 'FeaturedImage'>
      <a class='hotPosts__image flex-none' expr:href='data:i.url'>
        <b: con valor = 'datos: i.featuredImage? datos: i.featuredImage: datos: imgDefault 'var =' img '>
          <img expr: alt = 'data: i.title' expr: src = 'resizeImage (data: img, 80, "1: 1")' />
        </ b: con>
      </a>
    </ b: includable>
    <b: includable id = 'snippet'>
      <p class = 'hotPosts__snippet'> <b: eval expr = 'data: i.snippets.long snippet {length: 60}' /> </p>
    </ b: includable>
  </ b: widget>
</ b: sección>
</div>
</ b: si>

</ b: con> <b: comentario> Datos finales: showSidebar </ b: comentario>
</div> <! - .main__blog ->
</div> <! - .main ->

<footer class = "footer">
<div class = 'footer__primary'>
<b: section id = 'footer-copyright' maxwidgets = '2' class = 'contenedor skin-box bfix flx-yc justify-content-between flex-row-md flex-column'>
  <b: widget id = 'LinkList100' bloqueado = 'true' title = 'Redes sociales' tipo = 'LinkList'>
    <b: includable id = 'main'>
      <div class = 'socialList flx-yc flex-wrap'>
        <b: valores de bucle = 'datos: enlaces' var = 'i'>
          <a class='socialList-item flx-yc skin-color-hover' expr:href='data:i.target' rel='nofollow' target='_blank'>
            <i expr: class = 'data: i.name + "fa-mn"' />
          </a>
        </ b: bucle>
      </div> <! - .socialList ->
    </ b: includable>
  </ b: widget>
  <b: widget id = 'Text100' bloqueado = 'true' title = 'Copyright' type = 'Text'>
    <b: includable id = 'main'>
      <div class = 'footer__copy'>
        <span class = 'copy__date skin-font'> <data: blog.title /> 2019 </span>
        <b: comment> Este trabajo tiene la licencia de Creative Commons Attribution-NonCommercial 4.0 International License: http://creativecommons.org/licenses/by-nc/4.0/ </ b: comment>
        <div class = 'copy__attribution'>
          Creado por <a class='skin-color-hover' href='//zkreations.com' property='cc:attributionName' rel='nofollow' target='_blank'> zkreations </a> & amp; <a class='skin-color-hover' expr:href='data:blog.bloggerUrl' rel='nofollow' target='_blank'> Blogger </a> <data: content />
        </div>
      </div>
    </ b: includable>
  </ b: widget>
</ b: sección>
</div>

<b: section class = 'footerLinks' id = 'footerLinks' maxwidgets = '1'>
  <b: widget id = 'LinkList110' bloqueado = 'true' title = 'Enlaces de pie de página' tipo = 'LinkList' versión = '2'>
    <b: includable id = 'main'>
      <b: include name = 'content' />
    </ b: includable>
    <b: includable id = 'content'>
      <div class = 'skin-box flx-yc flex-wrap'>
        <b: valores de bucle = 'datos: enlaces' var = 'enlace'>
          <a class='footerLink' expr:href='data:link.target' target='_blank' rel='nofollow'>
            <i class = 'fas fa-link' /> <data: link.name/>
          </a>
        </ b: bucle>
      </div>
    </ b: includable>
  </ b: widget>
</ b: sección>
</footer>

</div> <! - .template ->
</div>

<! - PLANTILLA FINAL ->
<! - Todos VANILLA JS (Sin dependencia de marco) ->
<script src = 'https: //cdn.jsdelivr.net/gh/zkreations/whale@1.5.5/dist/js/whale.min.js'/>

<! - Pequeño control deslizante ->
<b: if cond = 'data: view.isHomepage'>
<script src = "// cdnjs.cloudflare.com/ajax/libs/tiny-slider/2.9.1/min/tiny-slider.js" />
<script> // <! [CDATA [
var carrusel = tns ({
    contenedor: '. carousel__content', nav: false, arrowKeys: false, useLocalStorage: false,
    items: 2, responsive: {576: {items: 3}, 768: {items: 4}, 992: {items: 5}},
    nextButton: '. controls__next', prevButton: '. controls__prev',
    canalón: 2,
    slideBy: 1,
    reproducción automática: verdadero,
    swipeAngle: falso,
    autoplayHoverPause: verdadero,
    autoplayButtonOutput: falso,
    mouseDrag: cierto,
    autoplayTimeout: 5000,
    bucle: falso,
    rebobinar: cierto,
    velocidad: 600
});
//]]> </script>
</ b: si>

<! - Font Awesome ->
<link rel = 'hoja de estilo' 
      media = 'print' onload = 'this.media = "all"' 
      href = 'https: //cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@5/css/all.min.css'/>
<noscript>
  <link rel = 'stylesheet' href = 'https: //cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@5/css/all.min.css'/>
</noscript>

<! - Animate.css ->
<link rel = "hoja de estilo" 
      media = "print" onload = "this.media = 'all'"
      href = "https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.0/animate.min.css" />
<noscript>
  <link rel = 'stylesheet' href = 'https: //cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.0/animate.min.css'/>
</noscript>

</ b: con> <b: comentario> Datos finales: diseño </ b: comentario>
</ b: con> <b: comentario> Datos finales: imgDefault </ b: comentario>

<! - Google Analytics ->
<b: include data = 'blog' name = 'google-analytics' />
</body>
</html>
