---
title: "Tecnologías comunes de web de lado cliente"
description: "Diseñar aplicaciones Web modernas con ASP.NET Core y Azure | Tecnologías comunes de web de lado cliente"
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e8e156552fd4aa733594c01845fb7ed1643b4aef
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="common-client-side-web-technologies"></a>Tecnologías comunes de Web de lado cliente

> "Sitios Web debe aparezcan correctamente desde el interior y out."  
> _-Paul Cookson_

## <a name="summary"></a>Resumen

Las aplicaciones de ASP.NET Core son aplicaciones web y normalmente se basan en tecnologías de cliente web como HTML, CSS y JavaScript. Al separar el contenido de la página (HTML) de su diseño y estilos (CSS) y su comportamiento (a través de JavaScript), aplicaciones web complejas pueden aprovechar el principio de separación de asuntos. Los cambios futuros en la estructura, el diseño o el comportamiento de la aplicación se pueden realizar más fácilmente cuando estos problemas no están entrelazados.

Mientras que HTML y CSS son relativamente estables, JavaScript, por medio de los marcos de aplicaciones y los desarrolladores de utilidades trabajan con para crear aplicaciones basadas en web, ha evolucionado a velocidad vértigo. En este capítulo se examina algunas maneras de que JavaScript se usa por los desarrolladores web como parte del desarrollo de aplicaciones, ya que proporciona una descripción general de las bibliotecas de lado cliente Angular y reaccionar.

## <a name="html"></a>HTML

HTML (lenguaje de marcado de hipertexto) es el lenguaje de marcado estándar que se utiliza para crear páginas web y aplicaciones web. Sus elementos forman los pilares de páginas, que representa texto con formato, imágenes, entradas de formulario y otras estructuras. Cuando un explorador realiza una solicitud a una dirección URL, si la obtención de una página o una aplicación, lo primero que es devuelto es un documento HTML. Este documento HTML puede hacer referencia o incluir información adicional sobre su apariencia y el diseño en forma de CSS, o el comportamiento en forma de JavaScript.

## <a name="css"></a>CSS

CSS (Cascading Style Sheets) se utiliza para controlar la apariencia y el diseño de los elementos HTML. Estilos CSS pueden aplicar directamente a un elemento HTML, definidos por separado en la misma página, o definidos en un archivo independiente y hace referencia a la página. Estilos en cascada en función de cómo se utilizan para seleccionar un elemento HTML determinado. Por ejemplo, un estilo puede aplicar a todo el documento, pero se reemplazaría por un estilo que se aplica a un elemento determinado. Del mismo modo, un estilo específico del elemento se reemplazaría por un estilo que se aplica a una clase CSS que se aplica al elemento, que a su vez se reemplazaría por un estilo que se dirige a una instancia específica de ese elemento (a través de su identificador). Figura 6-1

**Figura 6-1.** Reglas de especificidad de CSS, en orden.

![](./media/image6-1.png)

Es mejor mantener estilos en sus propios archivos de hoja de estilos independiente y usar basados en selección en cascada para implementar coherentes y reutilizables estilos dentro de la aplicación. Debe evitar colocar las reglas del estilo en HTML y aplicar estilos a los elementos individuales específicos (en lugar de clases completas de elementos, o los elementos que han tenido una clase determinada de CSS aplicada a ellos) debe ser una excepción, no la regla.

### <a name="css-preprocessors"></a>Preprocesadores CSS

Hojas de estilo CSS no tienen compatibilidad con lógica condicional, variables y otras características del lenguaje de programación. Por lo tanto, hojas de estilos grandes suelen incluyen una gran cantidad de repetición, como el mismo color, fuente u otra configuración se aplica a distintas variaciones de clases CSS y los elementos HTML. Preprocesadores CSS pueden ayudar a su hojas de estilos siguen la [principio SECA](http://deviq.com/don-t-repeat-yourself/) agregando compatibilidad para las variables y la lógica.

Los preprocesadores CSS más populares son Sass y menor. Ambos amplían CSS y son compatibles con versiones anteriores con él, lo que significa que un archivo CSS sin formato es un Sass válido o menos. SASS está basado en Ruby, menor es basada en JavaScript y normalmente se ejecutan ambos como parte del proceso de desarrollo local. Ambos tienen comandos herramientas de línea de soporte técnico disponible, así como integrada en Visual Studio para ejecutarlas con tareas Gulp o Grunt.

## <a name="javascript"></a>JavaScript

JavaScript es un lenguaje de programación dinámico, interpretado que ha normalizado en la especificación del lenguaje ECMAScript. Es el lenguaje de programación de la web. Como CSS, JavaScript puede definirse como atributos dentro de los elementos HTML, como bloques de script dentro de una página o en archivos independientes. Al igual que de CSS, se suele recomienda para organizar JavaScript en archivos independientes, y se mantiene separados tanto como sea posible desde el código HTML que se encuentra en las páginas web individuales o vistas de la aplicación.

Cuando se trabaja con JavaScript en la aplicación web, hay algunas tareas que normalmente debe realizar:

-   Al seleccionar un elemento HTML y recuperar o actualizar su valor

-   Consultar una API Web de datos

-   Enviar un comando a una API Web (y responder a una devolución de llamada con su resultado)

-   Realizar la validación

Puede realizar todas estas tareas con JavaScript por sí sola, pero existen muchas bibliotecas para que sea más fácil estas tareas. Uno de los primeros y más correcta de estas bibliotecas es jQuery, que sigue siendo una opción popular para simplificar estas tareas en páginas web. Para aplicaciones de página única (SPAs), jQuery no proporciona muchas de las funciones deseadas que ofrecen Angular y reaccionar.

### <a name="legacy-web-apps-with-jquery"></a>Aplicaciones Web heredado con jQuery

Aunque antiguas por los estándares de marco de trabajo de JavaScript, jQuery sigue siendo una biblioteca muy frecuente para trabajar con HTML/CSS y crear aplicaciones que realizan llamadas de AJAX a las API web. Sin embargo, jQuery funciona en el nivel del modelo de objetos de documento (DOM) de explorador y de forma predeterminada ofrece un modelo imperativo, en lugar de declarativo.

Por ejemplo, imagine que si el valor de un cuadro de texto superior a 10, un elemento de la página debe hacerse visible. En jQuery, esto normalmente se implementa mediante la escritura de un controlador de eventos con el código que inspeccionar el valor del cuadro de texto y establecer la visibilidad del elemento de destino basándose en ese valor. Se trata de un enfoque basado en código imperativo. Otro marco de trabajo en su lugar, puede usar el enlace de datos para enlazar mediante declaración la visibilidad del elemento en el valor del cuadro de texto. No necesitará escribir ningún código, pero en su lugar sólo requiere decorando los elementos relacionados con los atributos de enlace de datos. Según los comportamientos de lado cliente crecen más complejos, enlace de datos con frecuencia considera los resultados en las soluciones más simples con menos código y la complejidad condicional.

### <a name="jquery-vs-a-spa-framework"></a>jQuery vs un marco de trabajo de SPA

| **Factor** | **jQuery** | **angular**|
|--------------------------|------------|-------------|
| Abstrae el DOM | **Sí** | **Sí** |
| Compatibilidad con AJAX | **Sí** | **Sí** |
| Enlace de datos declarativo | **No** | **Sí** |
| Enrutamiento basado en MVC | **No** | **Sí** |
| Creación de plantillas | **No** | **Sí** |
| Vínculo profundo de enrutamiento | **No** | **Sí** |

La mayoría de las características que carece de jQuery intrínsecamente puede agregarse con la adición de otras bibliotecas. Sin embargo, un marco SPA como Angular proporciona estas características de forma más integrada, ya que se ha diseñado con todas las funciones en mente desde el principio. Además, jQuery es una biblioteca muy imperativa, lo que significa que debe llamar a funciones de jQuery para hacer nada con jQuery. Gran parte de la funcionalidad que proporcionan los marcos SPA y trabajo puede realizarse mediante declaración, que requieren que se escriba ningún código real.

Enlace de datos es un buen ejemplo de esto. En jQuery, normalmente basta con una línea de código para obtener el valor de un elemento DOM, o para establecer el valor de un elemento. Sin embargo, tendrá que escribir este código siempre que necesite cambiar el valor del elemento y, a veces, esto ocurrirá en varias funciones en una página. Otro ejemplo común es la visibilidad de los elementos. En jQuery, podría haber muchos lugares diferentes no donde se escribirá código para controlar si determinados elementos estaban visibles. En cada uno de estos casos, cuando utiliza un enlace de datos, no código tendría que escribir. Simplemente podría enlazar el valor o la visibilidad de los elementos en cuestión para un *viewmodel* en la página y cambia a lo que viewmodel automáticamente se reflejarán en los elementos de enlace.

### <a name="angular-spas"></a>SPAs angulares

AngularJS se convirtió rápidamente en uno de los marcos de JavaScript más populares del mundo. Con 2 Angular, el equipo vuelve a generar el marco de trabajo desde el principio seguridad (mediante [TypeScript](https://www.typescriptlang.org/)) y cambia el nombre de AngularJS para simplemente Angular. Actualmente en versión 4, Angular sigue siendo un marco robusto para la creación de aplicaciones de una única página.

Aplicaciones angulares se generan a partir de componentes. Componentes de combinan plantillas HTML con objetos especiales y controlan una parte de la página. Un componente simple de documentos del Angular se muestra aquí:

```js
import { Component } from '@angular/core';

@Component({
    selector: 'my-app',
    template: `<h1>Hello {{name}}</h1>`
})

export class AppComponent { name = 'Angular'; }
```

Los componentes se definen mediante el @Component función decorador, que tarda en los metadatos acerca del componente. La propiedad selector identifica el Id. del elemento en la página donde se mostrará este componente. La propiedad de plantilla es una plantilla sencilla que HTML que incluye un marcador de posición que corresponde a la propiedad de nombre del componente, definida en la última línea.

Al trabajar con componentes y las plantillas, en lugar de los elementos DOM, Angular aplicaciones pueden funcionar en un nivel más alto de abstracción y con menos código general que las aplicaciones escritas con solo JavaScript (también denominada "vainilla JS") o con jQuery. Angular también impone algún pedido en cómo organizar los archivos de script de cliente. Por convención, Angular aplicaciones utilizan una estructura de carpetas común, con los archivos de script de módulo y componente ubicados en una carpeta de la aplicación. Angulares secuencias de comandos que se trate a compilar, implementar y probar la aplicación normalmente se encuentran en una carpeta de nivel superior.

Angular también hace gran uso de herramientas de interfaz de línea de comandos (CLI). Introducción a Angular desarrollo localmente (suponiendo que ya tenga instalado de npm y git) consta de clonación simplemente un repositorio de GitHub y en ejecución \`instalar npm\` y \`npm inicio\`. Aparte de esto, Angular suministra su propia herramienta CLI que puede crear proyectos, agregar archivos y ayudar con las tareas de pruebas, la agrupación y la implementación. Esta CLI tooling facilidad uso hace que Angular especialmente sea compatible con ASP.NET Core, que también incluye soporte de CLI excelente.

Microsoft ha desarrollado una aplicación de referencia, [eShopOnContainers](http://aka.ms/MicroservicesArchitecture), que incluye una implementación de SPA Angular. Esta aplicación incluye módulos angulares para administrar la tienda en línea elementos de la cesta de compra, la carga y la presentación de su catálogo de la compra y controlar la creación del pedido. Puede ver y descargar la aplicación de ejemplo de [GitHub](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebSPA).

### <a name="react"></a>reaccionar

A diferencia de Angular, que ofrece una completa de implementación del modelo Model-View-Controller, reaccionar sólo se ocupa de vistas. No es un marco de trabajo, solo una biblioteca, por ello, para compilar un SPA debe aprovechar bibliotecas adicionales.

Una de las características más importantes de reaccionar es el uso de un DOM. virtual El DOM virtual proporciona reaccionan con varias ventajas, incluido el rendimiento (el DOM virtual puede optimizar qué partes del DOM real deben actualizarse) y capacidad de prueba (no es necesario tener un explorador para probar reaccionar y su interacción con su DOM virtual).

Reaccionar también es muy frecuente en funcionamiento con HTML. En lugar de tener una estricta separación entre el código y marcado (con referencias a JavaScript que aparecen en los atributos HTML quizás), reaccionar agrega HTML directamente en su código de JavaScript como JSX. JSX es la sintaxis de HTML que pueden compilar hasta JavaScript puro. Por ejemplo:

```js
<ul>
{ authors.map(author =>
    <li key={author.id}>{author.name}</li>
)}
</ul>
```

Si ya conoce JavaScript, aprendizaje reaccionan debería ser sencilla. No hay casi toda una curva de aprendizaje o una sintaxis especial implicados como con Angular u otras bibliotecas populares.

Porque reaccionan no es un marco de trabajo completo, normalmente querrá otras bibliotecas para controlar aspectos como el enrutamiento, web llamadas API y la administración de dependencias. Lo mejor es, puede elegir la biblioteca recomendada para cada uno de ellos, pero el inconveniente es que es necesario realizar todas estas decisiones y compruebe todas las bibliotecas elegidas funcionan bien juntos cuando haya terminado. Si desea que un buen punto de partida, puede usar un starter kit como Slingshot reaccionar, que envases un conjunto de bibliotecas compatibles con reaccionar.

### <a name="choosing-a-spa-framework"></a>Elegir un marco de trabajo SPA

Al considerar qué marco JavaScript funcionará mejor para admitir el SPA, tenga en cuenta las consideraciones siguientes:

-   ¿Se encuentra el equipo familiarizado con el marco de trabajo y sus dependencias (TypeScript incluido en algunos casos)?

-   Cómo opinionated es el marco de trabajo y ¿está de acuerdo con su modo predeterminado de hacer las cosas?

-   ¿(O a una biblioteca complementaria) incluye todas las características que requiere la aplicación?

-   ¿Está bien documentado?

-   ¿Cómo activo es su comunidad? ¿Creación de nuevos proyectos creados con él?

-   ¿Cómo activo es su equipo principal? ¿Se envían periódicamente que se va a versiones nuevas y resolver los problemas?

Marcos de JavaScript siguen evolucionando con una velocidad de vértigo. Utilice las consideraciones enumeradas anteriormente para ayudar a mitigar el riesgo de elección más adelante podrá conforme depende de un marco de trabajo. Si está especialmente perjudiciales riesgo, considere la posibilidad de un marco de trabajo que se ofrece soporte técnico comercial o está siendo desarrollado por una empresa de gran tamaño.

> ### <a name="references--client-web-technologies"></a>Referencias: tecnologías Web de cliente
> - **HTML y CSS**  
> <https://www.w3.org/standards/webdesign/htmlcss>
> - **SASS vs. LESS**  
> <https://www.keycdn.com/blog/sass-vs-less/>
> - **Aplicar un estilo a aplicaciones de ASP.NET Core con menos y Sass, fuente Maravilla**  
> <https://docs.microsoft.com/aspnet/core/client-side/less-sass-fa>
> - **Desarrollo de cliente en ASP.NET Core**  
> <https://docs.microsoft.com/aspnet/core/client-side/>
> - **jQuery**  
> <https://jquery.com/>
> - **jQuery vs AngularJS**  
> <https://www.airpair.com/angularjs/posts/jquery-angularjs-comparison-migration-walkthrough>
> - **angular**  
> <https://angular.io/>
> - reaccionar  
> <https://facebook.github.io/react/>
> - **Reaccionar Slingshot**  
> <https://github.com/coryhouse/react-slingshot>
> - **Reaccionar frente a Angular comparación 2**  
> <https://www.codementor.io/codementorteam/react-vs-angular-2-comparison-beginners-guide-lvz5710ha>
> - **5 mejores marcos de JavaScript de 2017**  
> <https://hackernoon.com/5-best-javascript-frameworks-in-2017-7a63b3870282>

>[!div class="step-by-step"]
[Previous] (common-web-application-architectures.md) [Next] (develop-asp-net-core-mvc-apps.md)
