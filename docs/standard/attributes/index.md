---
title: Extender metadatos mediante atributos
description: Obtenga información sobre cómo ampliar los metadatos mediante atributos en .NET. Los atributos son declaraciones descriptivas, similares a las palabras clave, para anotar elementos de programación, como es el caso de los tipos y los campos.
ms.date: 10/14/2020
helpviewer_keywords:
- metadata, extending
- attributes [.NET], metadata
- elements [.NET], attributes
- common language runtime, attributes
- annotating programming elements
- keyword-like descriptive declarations
- runtime, attributes
- extending metadata
ms.assetid: 30386922-1e00-4602-9ebf-526b271a8b87
ms.openlocfilehash: e41299b83ae451117ab6829eee928b0d2306be19
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829081"
---
# <a name="extend-metadata-using-attributes"></a>Ampliación de los metadatos mediante atributos

Common Language Runtime permite agregar declaraciones descriptivas a modo de palabras clave, conocidas como atributos, para anotar elementos de programación como tipos, campos, métodos y propiedades. Cuando compila el código para runtime, este se convierte al Lenguaje Intermedio de Microsoft (MSIL) y se coloca dentro de un archivo portable ejecutable (PE) junto con los metadatos generados por el compilador. Los atributos permiten colocar información descriptiva adicional en los metadatos que se puede extraer usando servicios de reflexión en tiempo de ejecución. El compilador crea atributos cuando se declaran instancias de clases especiales que derivan de <xref:System.Attribute?displayProperty=nameWithType>.

.NET usa atributos por distintos motivos y para tratar diversos problemas. Los atributos describen cómo serializar los datos, especifican las características que se usan para aplicar la seguridad y limita las optimizaciones del compilador Just-In-Time (JIT) para que el código siga siendo fácil de depurar. Los atributos también pueden registrar el nombre de un archivo o el autor del código, o controlar la visibilidad de controles y los miembros durante el desarrollo de formularios.

## <a name="related-articles"></a>Artículos relacionados

|Title|Descripción|
|-----------|-----------------|
|[Aplicar atributos](applying-attributes.md)|Describe cómo aplicar un atributo a un elemento del código.|
|[Escribir atributos personalizados](writing-custom-attributes.md)|Describe cómo diseñar clases de atributos personalizados.|
|[Recuperar la información almacenada en atributos](retrieving-information-stored-in-attributes.md)|Describe cómo recuperar los atributos personalizados del código que se carga en el contexto de ejecución.|
|[Metadatos y componentes autodescriptivos](../metadata-and-self-describing-components.md)|Proporciona información general de los metadatos y describe cómo se implementan en un archivo portable ejecutable (PE) de .NET.|
|[Cómo: Cargar ensamblados en el contexto de solo reflexión](../../framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)|Explica cómo recuperar la información de los atributos personalizados en el contexto de solo reflexión.|

## <a name="reference"></a>Referencia

- <xref:System.Attribute?displayProperty=nameWithType>
