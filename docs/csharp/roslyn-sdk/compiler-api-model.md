---
title: Modelo de objetos y conceptos del SDK de .NET Compiler Platform
description: En este tema se proporciona la información necesaria para trabajar de forma eficaz con el SDK de .NET Compiler. Aprenderá sobre las capas de API, los tipos principales implicados y el modelo de objetos general.
ms.date: 07/13/2020
ms.custom: mvc
ms.openlocfilehash: a65d282dd3c58279bbfd635c0386d50ce3f30055
ms.sourcegitcommit: e7748001b1cee80ced691d8a76ca814c0b02dd9b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86374473"
---
# <a name="understand-the-net-compiler-platform-sdk-model"></a>Descripción del modelo del SDK de .NET Compiler Platform

Los compiladores procesan el código que se escribe conforme a reglas estructuradas que a menudo se diferencian de la forma en que los seres humanos lo leen y lo entienden. Una comprensión básica del modelo usado por los compiladores resulta fundamental para entender las API que se usan al compilar herramientas basadas en Roslyn.

## <a name="compiler-pipeline-functional-areas"></a>Áreas funcionales de canalización de compilador

El SDK de .NET Compiler Platform expone el análisis de código de los compiladores de C# y Visual Basic al proporcionar una capa de API que refleja una canalización de compilador tradicional.

![Pasos del código fuente de procesamiento de canalización de compilador a código de objeto](media/compiler-api-model/compiler-pipeline.png)

Cada fase de esta canalización es un componente independiente. En primer lugar, la fase de análisis acorta y analiza el texto de origen en la sintaxis que sigue la gramática del lenguaje. En segundo lugar, la fase de declaración analiza los metadatos importados y de origen para formar símbolos con nombre. Luego, la fase de enlace combina los identificadores del código con los símbolos. Por último, en la fase de emisión se emite un ensamblado con toda la información generada por el compilador.

![La API de canalización de compilador proporciona acceso a cada paso que forma parte de la canalización de compilador.](media/compiler-api-model/compiler-pipeline-api.png)

En correspondencia a cada una de esas fases, el SDK de .NET Compiler Platform expone un modelo de objetos que permite el acceso a la información en esa fase. La fase de análisis expone un árbol de sintaxis, la fase de declaración expone una tabla de símbolos jerárquica, la fase de enlace expone el resultado del análisis semántico del compilador y la fase de emisión es una API que genera códigos de bytes de IL.

![Servicios de lenguaje disponibles desde la API del compilador en cada paso de la canalización de compilador](media/compiler-api-model/compiler-pipeline-lang-svc.png)

Cada compilador combina estos componentes como un único todo.

Estas API son las mismas que usa Visual Studio. Por ejemplo, las características de formato y esquema del código usan los árboles de sintaxis, las características de navegación y el **Examinador de objetos** usan la tabla de símbolos, las refactorizaciones e **Ir a definición** usan el modelo semántico, y **Editar y continuar** usa todos ellos, incluida la API de emisión.

## <a name="api-layers"></a>Capas de API

El SDK del compilador de .NET consta de varias capas de API: de compilador, de diagnóstico, de scripting y de área de trabajo.

### <a name="compiler-apis"></a>API de compilador

La capa de compilador contiene los modelos de objetos que corresponden con la información expuesta en cada fase de la canalización de compilador, sintáctica y semántica. La capa de compilador también contiene una instantánea inmutable de una sola invocación de un compilador, incluidas las referencias de ensamblado, las opciones del compilador y los archivos de código fuente. Hay dos API distintas que representan el lenguaje C# y el lenguaje Visual Basic. Las dos API son similares en forma, aunque están adaptadas para lograr una alta fidelidad con cada lenguaje. Esta capa no tiene dependencias en componentes de Visual Studio.

### <a name="diagnostic-apis"></a>API de diagnóstico

Como parte de su análisis, el compilador puede generar un conjunto de diagnósticos que abarcan desde errores de sintaxis, semántica y asignación definitiva hasta distintas advertencias y diagnósticos informativos. La capa de la API de compilador expone diagnósticos a través de una API extensible que permite incluir analizadores definidos por el usuario en el proceso de compilación. Permite generar diagnósticos definidos por el usuario, como los de herramientas como StyleCop o FxCop, junto con diagnósticos definidos por el compilador. La generación de diagnósticos de este modo tiene la ventaja de integrarse de forma natural con herramientas como MSBuild y Visual Studio, que dependen de diagnósticos de experiencias como detener una compilación según una directiva y mostrar subrayados ondulados activos en el editor y sugerir correcciones de código.

### <a name="scripting-apis"></a>API de scripting

Las API de hospedaje y scripting forman parte de la capa de compilador. Puede usarlas para ejecutar fragmentos de código y acumular un contexto de ejecución en tiempo de ejecución.
El REPL (bucle de lectura, evaluación e impresión) interactivo de C# usa estas API. El REPL permite usar C# como lenguaje de scripting, al ejecutar el código de forma interactiva mientras se escribe.

### <a name="workspaces-apis"></a>API de áreas de trabajo

La capa de áreas de trabajo contiene la API de área de trabajo, que es el punto de partida para realizar análisis de código y refactorización de soluciones completas. Ayuda a organizar toda la información sobre los proyectos de una solución en un modelo de objetos único, lo que ofrece acceso directo a los modelos de objetos de capa de compilador sin necesidad de analizar archivos, configurar opciones ni administrar dependencias entre proyectos.

Además, la capa de áreas de trabajo expone un conjunto de API que se usa al implementar las herramientas de análisis de código y refactorización que funcionan en un entorno de host como el IDE de Visual Studio. Los ejemplos incluyen las API Buscar todas las referencias, Formato y Generación de código.

Esta capa no tiene dependencias en componentes de Visual Studio.
