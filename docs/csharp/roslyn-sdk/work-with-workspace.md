---
title: Trabajar con el modelo de área de trabajo del SDK de .NET Compiler Platform
description: En este tema se proporciona una descripción del tipo que se usa para consultar y manipular el área de trabajo y los proyectos del código.
ms.date: 10/15/2017
ms.custom: mvc
ms.openlocfilehash: d21873b132d5f0788033693a319e556feeac59a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156888"
---
# <a name="work-with-a-workspace"></a>Trabajar con un área de trabajo

La capa **Áreas de trabajo** es el punto de partida para realizar análisis de código y refactorización de soluciones completas. En esta capa, la API de área de trabajo ayuda a organizar toda la información sobre los proyectos de una solución en un modelo de objetos único, lo que ofrece acceso directo a modelos de objetos de capa de compilador como texto de origen, árboles de sintaxis, modelos semánticos y compilaciones sin necesidad de analizar archivos, configurar opciones ni administrar dependencias entre proyectos.

Los entornos de host, como un IDE, proporcionan un área de trabajo que corresponde a la solución abierta. También es posible usar este modelo fuera de un IDE con solo cargar un archivo de solución.

## <a name="workspace"></a>Área de trabajo

Un área de trabajo es una representación activa de la solución como una colección de proyectos, cada uno con una colección de documentos. Normalmente, un área de trabajo está asociada a un entorno de host en continuo cambio a medida que el usuario escribe o manipula las propiedades.

<xref:Microsoft.CodeAnalysis.Workspace> proporciona acceso al modelo actual de la solución. Cuando se produce un cambio en el entorno de host, el área de trabajo desencadena los eventos correspondientes y la propiedad <xref:Microsoft.CodeAnalysis.Workspace.CurrentSolution?displayProperty=nameWithType> se actualiza. Por ejemplo, cuando el usuario escribe en un editor de texto correspondiente a uno de los documentos de origen, el área de trabajo usa un evento para indicar que ha cambiado el modelo general de la solución y qué documento se ha modificado. Luego puede reaccionar a esos cambios mediante el análisis de la corrección del nuevo modelo, resaltando las áreas de importancia o realizando una sugerencia para un cambio de código.

También puede crear áreas de trabajo independientes desconectadas del entorno de host o que se usen en una aplicación sin entorno de host.

## <a name="solutions-projects-documents"></a>Soluciones, proyectos, documentos

Aunque un área de trabajo puede cambiar cada vez que se pulsa una tecla, puede trabajar con el modelo de la solución de forma aislada.

Una solución es un modelo inmutable de los proyectos y los documentos. Esto significa que el modelo se puede compartir sin que haya bloqueo ni duplicación. Después de obtener una instancia de solución de la propiedad <xref:Microsoft.CodeAnalysis.Workspace.CurrentSolution?displayProperty=nameWithType>, esa instancia no cambia nunca. Pero, al igual que con los árboles de sintaxis y las compilaciones, puede modificar soluciones mediante la creación de nuevas instancias basadas en soluciones existentes y cambios concretos. Para que el área de trabajo refleje los cambios, debe aplicar explícitamente la solución modificada al área de trabajo.

Un proyecto es una parte del modelo de solución general inmutable. Representa todos los documentos de código de origen, las opciones de análisis y compilación, y las referencias de ensamblado y de proyecto a proyecto. Desde un proyecto puede acceder a la compilación correspondiente sin necesidad de determinar las dependencias del proyecto ni de analizar los archivos de origen.

Un documento también es una parte del modelo de solución general inmutable. Un documento representa un solo archivo de origen desde el que se puede acceder al texto del archivo, el árbol de sintaxis y el modelo semántico.

El diagrama siguiente es una representación de la relación entre el área de trabajo y el entorno de host, las herramientas y cómo se realizan las modificaciones.

![Relaciones entre los distintos elementos de un área de trabajo que contiene proyectos y archivos de origen](media/work-with-workspace/workspace-obj-relations.png)

## <a name="summary"></a>Resumen

Roslyn expone un conjunto de API de compilador y API de áreas de trabajo que proporciona información detallada sobre el código fuente y que tiene plena fidelidad con los lenguajes C# y Visual Basic.  El SDK de .NET Compiler Platform reduce notablemente la barrera para crear herramientas y aplicaciones centradas en el código. Crea numerosas oportunidades para la innovación en áreas como la metaprogramación, la generación y la transformación de código, el uso interactivo de los lenguajes C# y Visual Basic, y la inserción de C# y Visual Basic en lenguajes específicos del dominio.  
