---
title: 'Configurar los proyectos (F #)'
description: "Obtenga información acerca de cómo utilizar el Diseñador de proyectos cuando se trabaja con proyectos de F # en Visual Studio."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8b2ed206-34e4-4256-a6ce-0c2499561165
ms.openlocfilehash: f56fed1e16b4de1d97766f37cb1c72297d5502d5
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2017
---
# <a name="configuring-projects-in-visual-studio"></a>Configurar los proyectos en Visual Studio

> [!NOTE]
En este artículo no está actualizado con el más reciente de Visual Studio.  Se va a actualizar.

Este tema incluye información sobre cómo usar el **Diseñador de proyectos** cuando se trabaja con proyectos de F #. Trabajar con proyectos de F # no es significativamente diferente de trabajar con proyectos de Visual Basic o C#. A menudo puede utilizar la documentación general de proyecto de Visual Studio como referencia principal cuando se usa F #. En este tema se proporciona vínculos a información relevante en la documentación de Visual Studio para la configuración que se comparten con otros lenguajes de Visual Studio y también se describe la configuración específica de F #.

## <a name="project-designer"></a>Diseñador de proyectos
El **Diseñador de proyectos** y su uso general se describen totalmente en el tema [Introducción al diseñador de proyectos](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7) en la documentación de Visual Studio. El **Diseñador de proyectos** consta de varias páginas agrupadas por funcionalidades relacionadas. Las páginas disponibles para los proyectos de F # son principalmente un subconjunto de los que están disponibles para otros idiomas. En la tabla siguiente, se describen las páginas admitidas en F #. Las páginas que no están disponibles se relacionan con características que no están disponibles en F #, o que están disponibles mediante el cambio de una opción de línea de comandos. Las páginas que están disponibles en F # son similares a las páginas de C# más fielmente, por lo que se proporciona un vínculo relevante C# **Diseñador de proyectos** página.

|Página del Diseñador de proyectos|Vínculos relacionados|Descripción|
|---------------------|-------------|-----------|
|`Application`|[Página de aplicación, Diseñador de proyectos &#40; C &#35; &#41;](https://msdn.microsoft.com/library/ms247046.aspx)|Le permite especificar la configuración del nivel de aplicación y las propiedades, por ejemplo, si está creando una biblioteca o un archivo ejecutable, qué versión de .NET Framework en la que está destinada la aplicación e información sobre donde el archivo de recursos que la aplicación usa está almacenadas.|
|`Build`|[Generar página, Diseñador de proyectos &#40; C &#35; &#41;](https://msdn.microsoft.com/library/kb4wyys2.aspx)|Le permite controlar cómo se compila el código.|
|`Build Events`|[Crear página de eventos, Diseñador de proyectos &#40; C &#35; &#41;](https://msdn.microsoft.com/library/kb4wyys2.aspx)|Le permite especificar comandos que se ejecuten antes o después de la compilación.|
|`Debug`|[Página Depuración, Diseñador de proyectos](https://msdn.microsoft.com/library/2wcdezs5.aspx)|Le permite controlar cómo se ejecuta la aplicación durante la depuración. Esto incluye qué línea de comandos que se usará y ¿qué es el directorio de inicio de la aplicación y cualquier especiales que desea habilitar, como código nativo y SQL de modos de depuración.|
|`Reference Paths`|[Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)|Le permite especificar dónde buscar los ensamblados que depende el código.|

## <a name="f-specific-settings"></a>F #-configuración específica
En la tabla siguiente resume la configuración que es específicos de F #:

|Página del Diseñador de proyectos|Parámetro|Descripción|
|---------------------|-------|-----------|
|`Build`|`Generate tail calls`|Si se selecciona, habilita el uso de la instrucción del lenguaje intermedio (MSIL) de Microsoft de la cola. Esto hace que el marco de pila para reutilizarse en funciones recursivas de cola. Equivalente a la `--tailcalls` opción del compilador.|
|`Build`|`Other flags`|Permite especificar opciones de línea de comandos del compilador adicionales.|

## <a name="see-also"></a>Vea también
 [Empezar a trabajar con F # en Visual Studio](../get-started/get-started-visual-studio.md)  
 [Opciones del compilador](../language-reference/compiler-options.md)  
 [Introducción al Diseñador de proyectos](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7(v=vs.100))
