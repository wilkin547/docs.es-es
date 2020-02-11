---
title: Tecnologías web comunes del lado cliente
description: Diseño de aplicaciones web modernas con ASP.NET Core y Azure | Tecnologías web comunes del lado cliente
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: 7dd3765b1b71d8c1ef22d714a00be3e171fab523
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093128"
---
# <a name="common-client-side-web-technologies"></a>Tecnologías web comunes del lado cliente

> "Los sitios web deben tener una apariencia correcta, tanto interna como externa".  
> _- Paul Cookson_

Las aplicaciones ASP.NET Core son aplicaciones web y normalmente se basan en tecnologías web del lado cliente como HTML, CSS y JavaScript. Al separar el contenido de la página (HTML) de su diseño y estilos (CSS), y su comportamiento (a través de JavaScript), las aplicaciones web complejas pueden aprovechar el principio de separación de intereses. Los cambios futuros en la estructura, el diseño o el comportamiento de la aplicación se pueden realizar más fácilmente cuando estos intereses no están entrelazados.

Mientras que HTML y CSS son relativamente estables, JavaScript, por medio de los marcos de aplicaciones y los desarrolladores de utilidades con los que trabajan para crear aplicaciones basadas en web, ha evolucionado a velocidad vértigo. En este capítulo se examinan algunas maneras en las que los desarrolladores web usan JavaScript y se proporciona una descripción general de las bibliotecas del lado cliente Angular y React.

## <a name="html"></a>HTML

HTML (Lenguaje de marcado de hipertexto) es el lenguaje de marcado estándar que se usa para crear páginas web y aplicaciones web. Sus elementos forman los bloques de creación de las páginas y representan texto con formato, imágenes, entradas de formulario y otras estructuras. Cuando un explorador realiza una solicitud a una dirección URL, con independencia de que se obtenga una página o una aplicación, lo primero que se devuelve es un documento HTML. Este documento HTML puede hacer referencia o incluir información adicional sobre su apariencia y diseño en forma de CSS, o el comportamiento en forma de JavaScript.

## <a name="css"></a>CSS

CSS (Hoja de estilos en cascada) se usa para controlar la apariencia y el diseño de los elementos HTML. Los estilos CSS se pueden aplicar directamente a un elemento HTML, o bien definirse por separado en la misma página o en un archivo independiente al que la página haga referencia. Los estilos se aplican en cascada en función de cómo se usan para seleccionar un elemento HTML determinado. Por ejemplo, es posible que un estilo se aplique a todo el documento, pero que se reemplace por un estilo que se aplica a un elemento determinado. Del mismo modo, un estilo específico del elemento se reemplazaría por un estilo que se aplica a una clase CSS aplicada al elemento, que a su vez se reemplazaría por un estilo destinado a una instancia específica de ese elemento (a través de su identificador). Figura 6-1

![Reglas de especificidad de CSS](./media/image6-1.png)

**Figura 6-1.** Reglas de especificidad de CSS, en orden.

Se recomienda mantener los estilos en sus propios archivos de hoja de estilos independientes y aplicarlos en cascada en función de la selección para implementar estilos coherentes y reutilizables dentro de la aplicación. Se debe evitar colocar las reglas de estilo en el código HTML y aplicar estilos a elementos individuales específicos (en lugar de clases completas de elementos, o bien elementos a los que se ha aplicado una clase CSS determinada) debería ser la excepción, no la regla.

### <a name="css-preprocessors"></a>Preprocesadores CSS

Las hojas de estilo CSS carecen de compatibilidad con la lógica condicional, las variables y otras características de los lenguajes de programación. Por tanto, las hojas de estilo grandes suelen incluir una gran cantidad de repetición, ya que el mismo color, fuente u otra configuración se aplica a distintas variaciones de elementos HTML y clases CSS. Los preprocesadores CSS pueden ayudar a que las hojas de estilo sigan el [Principio DRY](https://deviq.com/don-t-repeat-yourself/) agregando compatibilidad para las variables y la lógica.

Los preprocesadores CSS más populares son Sass y LESS. Ambos amplían CSS y son compatibles con las versiones anteriores, lo que significa que un archivo CSS sin formato es un archivo Sass o LESS válido. Sass está basado en Ruby y LESS en JavaScript, y normalmente ambos se ejecutan como parte del proceso de desarrollo local. Los dos tienen herramientas de línea de comandos y compatibilidad integrada en Visual Studio para ejecutarlos con tareas Gulp o Grunt.

## <a name="javascript"></a>JavaScript

JavaScript es un lenguaje de programación interpretado y dinámico que se ha estandarizado en la especificación del lenguaje ECMAScript. Es el lenguaje de programación de la web. Como CSS, JavaScript se puede definir como atributos dentro de los elementos HTML, como bloques de script dentro de una página o en archivos independientes. Al igual que CSS, se recomienda organizar JavaScript en archivos independientes, y mantenerlos separados tanto como sea posible del código HTML que se encuentra en las páginas web individuales o vistas de la aplicación.

Cuando se trabaja con JavaScript en la aplicación web, hay algunas tareas que normalmente es necesario realizar:

- Seleccionar un elemento HTML y recuperar o actualizar su valor.

- Consultar datos en una API web.

- Enviar un comando a una API web (y responder a una devolución de llamada con su resultado).

- Realizar la validación.

Todas estas tareas se pueden realizar con JavaScript por sí solo, pero existen muchas bibliotecas para facilitarlas. Una de las primeras de estas bibliotecas y de mayor éxito es jQuery, que sigue siendo una opción popular para simplificar estas tareas en las páginas web. Para aplicaciones de página única (SPA), jQuery no proporciona muchas de las características deseadas que ofrecen Angular y React.

### <a name="legacy-web-apps-with-jquery"></a>Aplicaciones web heredadas con jQuery

Aunque de acuerdo con los estándares de marco de trabajo de JavaScript se considere antigua, jQuery sigue siendo una biblioteca de uso común para trabajar con HTML y CSS, y crear aplicaciones que realizan llamadas AJAX a las API web. Pero jQuery funciona en el nivel del modelo de objetos de documento (DOM) del explorador y, de forma predeterminada, ofrece un modelo imperativo, en lugar de declarativo.

Por ejemplo, imagine que, si el valor de un cuadro de texto es superior a 10, se deba mostrar un elemento en la página. En jQuery, esto normalmente se implementaría mediante la escritura de un controlador de eventos con código que inspeccionaría el valor del cuadro de texto y establecería la visibilidad del elemento de destino en función de ese valor. Se trata de un enfoque imperativo basado en código. Es posible que, en su lugar, otro marco de trabajo usara el enlace de datos para enlazar mediante declaración la visibilidad del elemento al valor del cuadro de texto. Con esto no sería necesario escribir código, solo habría que decorar los elementos implicados con atributos de enlace de datos. Cuando aumenta la complejidad de los comportamientos del lado cliente, los enfoques de enlace de datos suelen dar como resultado soluciones más simples con menos código y complejidad condicional.

### <a name="jquery-vs-a-spa-framework"></a>Diferencias entre jQuery y un marco de trabajo de SPA

| **Factor** | **jQuery** | **Angular**|
|--------------------------|------------|-------------|
| Abstrae el DOM | **Sí** | **Sí** |
| Compatibilidad con AJAX | **Sí** | **Sí** |
| Enlace de datos declarativo | **No** | **Sí** |
| Enrutamiento de estilo MVC | **No** | **Sí** |
| Plantillas | **No** | **Sí** |
| Enrutamiento de vínculo profundo | **No** | **Sí** |

La mayoría de las características de las que jQuery carece intrínsecamente se pueden agregar con la adición de otras bibliotecas. Pero un marco de SPA como Angular proporciona estas características de forma más integrada, ya que se ha diseñado con todas esas funciones en mente desde el principio. Además, jQuery es una biblioteca imperativa, lo que significa que se debe llamar a funciones de jQuery para realizar cualquier operación con jQuery. Gran parte del trabajo y la funcionalidad que proporcionan los marcos de SPA se puede realizar mediante declaración, lo que no requiere escribir ningún código.

El enlace de datos es un buen ejemplo de esto. En jQuery, normalmente basta con una línea de código para obtener el valor de un elemento DOM, o bien para establecer el valor de un elemento. Pero tendrá que escribir este código siempre que necesite cambiar el valor del elemento y, a veces, esto ocurrirá en varias funciones de una página. Otro ejemplo común es la visibilidad de los elementos. En jQuery, es posible que haya muchos lugares diferentes en los que tendría que escribir código para controlar si determinados elementos son visibles. En cada uno de estos casos, cuando se usa el enlace de datos, no sería necesario escribir código. Simplemente se podría enlazar el valor o la visibilidad de los elementos en cuestión a un *modelo de vista* en la página y los cambios en ese modelo de vista se reflejarán automáticamente en los elementos enlazados.

### <a name="angular-spas"></a>SPA de Angular

AngularJS se convirtió rápidamente en uno de los marcos de JavaScript más populares del mundo. Con Angular 2, el equipo recompiló el marco de trabajo desde el principio (mediante [TypeScript](https://www.typescriptlang.org/)) y cambió el nombre de AngularJS a simplemente Angular. Actualmente en la versión 4, Angular sigue siendo un marco robusto para la creación de aplicaciones de página única.

Las aplicaciones de Angular se compilan a partir de componentes. Los componentes combinan plantillas HTML con objetos especiales y controlan una parte de la página. Aquí se muestra un componente simple de la documentación de Angular:

```js
import { Component } from '@angular/core';

@Component({
    selector: 'my-app',
    template: `<h1>Hello {{name}}</h1>`
})

export class AppComponent { name = 'Angular'; }
```

Los componentes se definen mediante la función decorador @Component, que acepta metadatos sobre el componente. La propiedad selector identifica el identificador del elemento en la página donde se va a mostrar este componente. La propiedad template es una plantilla HTML sencilla que incluye un marcador de posición que corresponde a la propiedad name del componente, definida en la última línea.

Al trabajar con componentes y plantillas, en lugar de elementos DOM, las aplicaciones de Angular pueden funcionar en un nivel de abstracción más alto y con menos código general que las aplicaciones escritas solo con JavaScript (también denominadas "vanilla JS") o con jQuery. Angular también impone un orden sobre cómo organizar los archivos de script del lado cliente. Por convención, las aplicaciones de Angular usan una estructura de carpetas común, con los archivos de script de módulos y componentes ubicados en una carpeta de la aplicación. Los scripts de Angular relacionados con la compilación, implementación y pruebas de la aplicación normalmente se encuentran en una carpeta de nivel superior.

Puede desarrollar aplicaciones de Angular mediante una CLI. La introducción al desarrollo local de Angular (suponiendo que ya se haya instalado npm y git) consiste en clonar simplemente un repositorio de GitHub y ejecutar `npm install` y `npm start`. Aparte de esto, Angular suministra su propia CLI que puede crear proyectos, agregar archivos y ayudar con las tareas de pruebas, agrupación e implementación. Esta facilidad de uso de la CLI hace que Angular sea especialmente compatible con ASP.NET Core, que también incluye una excelente compatibilidad con la CLI.

Microsoft ha desarrollado una aplicación de referencia, [eShopOnContainers](https://aka.ms/MicroservicesArchitecture), que incluye una implementación de SPA de Angular. Esta aplicación incluye módulos de Angular para administrar la cesta de la compra de la tienda en línea, cargar y presentar los artículos del catálogo y controlar la creación de pedidos. Puede ver y descargar la aplicación de ejemplo en [GitHub](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebSPA).

### <a name="react"></a>React

A diferencia de Angular, que ofrece una implementación completa del modelo Model-View-Controller, React solo se ocupa de las vistas. No es un marco de trabajo, solo es una biblioteca, de modo que para compilar una SPA se debe recurrir a bibliotecas adicionales.

Una de las características más importantes de React es el uso de un DOM virtual. El DOM virtual proporciona varias ventajas a React, incluido el rendimiento (el DOM virtual puede optimizar las partes del DOM real que se deben actualizar) y la capacidad de prueba (no se necesita un explorador para probar React y sus interacciones con el DOM virtual).

El funcionamiento de React con HTML también es muy particular. En lugar de tener una separación estricta entre el código y el marcado (posiblemente con referencias a JavaScript en los atributos HTML), React agrega HTML directamente en su código de JavaScript como JSX. JSX es la sintaxis de estilo HTML que se puede compilar hasta JavaScript puro. Por ejemplo:

```js
<ul>
{ authors.map(author =>
    <li key={author.id}>{author.name}</li>
)}
</ul>
```

Si ya conoce JavaScript, el aprendizaje de React debería ser sencillo. No hay tanta curva de aprendizaje o una sintaxis especial como sucede con Angular u otras bibliotecas populares.

Como React no es un marco de trabajo completo, normalmente le interesarán otras bibliotecas para controlar aspectos como el enrutamiento, las llamadas a API web y la administración de dependencias. Lo mejor es que se puede elegir la mejor biblioteca para cada uno de estos aspectos, pero el inconveniente es que será necesario tomar todas estas decisiones y comprobar que todas las bibliotecas elegidas funcionan bien de forma conjunta cuando se haya terminado. Si quiere un buen punto de partida, puede usar un starter kit como React Slingshot, en el que se preempaqueta un conjunto de bibliotecas compatibles con React.

### <a name="choosing-a-spa-framework"></a>Elección de un marco de trabajo de SPA

Al considerar qué marco JavaScript funcionará mejor para admitir la SPA, tenga en cuenta las consideraciones siguientes:

- ¿El equipo está familiarizado con el marco de trabajo y sus dependencias (incluido TypeScript en algunos casos)?

- ¿Qué opiniones suscita el marco de trabajo; está de acuerdo con su modo predeterminado de hacer las cosas?

- ¿Incluye (o bien una biblioteca complementaria) todas las características que requiere la aplicación?

- ¿Está bien documentado?

- ¿Qué nivel de actividad tiene su comunidad? ¿Se compilan proyectos nuevos con él?

- ¿Qué nivel de actividad tiene su equipo principal? ¿Se resuelven los problemas y se publican periódicamente versiones nuevas?

Los marcos de JavaScript siguen evolucionando a una velocidad de vértigo. Use las consideraciones enumeradas anteriormente para ayudar a mitigar el riesgo de elegir un marco del que más adelante se arrepienta de depender. Si es especialmente reacio a los riesgos, considere la posibilidad de un marco de trabajo que ofrezca soporte técnico comercial o esté desarrollado por una gran empresa.

> ### <a name="references--client-web-technologies"></a>Referencias: tecnologías web cliente
>
> - **HTML y CSS**  
> <https://www.w3.org/standards/webdesign/htmlcss>
> - **Sass vs. LESS** (Diferencias entre Sass y LESS)  
> <https://www.keycdn.com/blog/sass-vs-less/>
> - **Aplicación de estilos a aplicaciones ASP.NET Core con LESS, Sass y Font Awesome**  
> <https://docs.microsoft.com/aspnet/core/client-side/less-sass-fa>
> - **Desarrollo del lado cliente en ASP.NET Core**  
> <https://docs.microsoft.com/aspnet/core/client-side/>
> - **jQuery**  
> <https://jquery.com/>
> - **jQuery vs AngularJS** (Diferencias entre jQuery y AngularJS)  
> <https://www.airpair.com/angularjs/posts/jquery-angularjs-comparison-migration-walkthrough>
> - **Angular**  
> <https://angular.io/>
> - **React**  
> <https://facebook.github.io/react/>
> - **React Slingshot**  
> <https://github.com/coryhouse/react-slingshot>
> - **React vs Angular 2 Comparison** (Comparación entre React y Angular 2)  
> <https://www.codementor.io/codementorteam/react-vs-angular-2-comparison-beginners-guide-lvz5710ha>
> - **5 Best JavaScript Frameworks of 2017** (Los 5 mejores marcos de trabajo JavaScript de 2017)  
> <https://hackernoon.com/5-best-javascript-frameworks-in-2017-7a63b3870282>

>[!div class="step-by-step"]
>[Anterior](common-web-application-architectures.md)
>[Siguiente](develop-asp-net-core-mvc-apps.md)
