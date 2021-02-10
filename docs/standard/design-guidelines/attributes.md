---
description: 'Más información acerca de: Atributos'
title: Atributos
ms.date: 10/22/2008
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
ms.openlocfilehash: 1557ba0945da0c8498c67f70ba4a01dd0bbe432e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642427"
---
# <a name="attributes"></a>Atributos

<xref:System.Attribute?displayProperty=nameWithType> es una clase base que se usa para definir atributos personalizados.

 Los atributos son anotaciones que se pueden agregar a elementos de programación como ensamblados, tipos, miembros y parámetros. Se almacenan en los metadatos del ensamblado y se puede tener acceso a ellos en tiempo de ejecución mediante las API de reflexión. Por ejemplo, el marco define el atributo <xref:System.ObsoleteAttribute>, que se puede aplicar a un tipo o un miembro para indicar que el tipo o miembro está en desuso.

 Los atributos pueden tener una o varias propiedades que contienen datos adicionales relacionados con el atributo. Por ejemplo, `ObsoleteAttribute` podría incluir información adicional sobre en qué versión un tipo o un miembro quedó en desuso, así como la descripción de las nuevas API que reemplazan a la API obsoleta.

 Se deben especificar algunas propiedades de un atributo cuando se aplica el atributo. Estas se conocen como "propiedades requeridas" o "argumentos necesarios", porque se representan como parámetros del constructor posicional. Por ejemplo, la propiedad <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> del atributo <xref:System.Diagnostics.ConditionalAttribute> es una propiedad obligatoria.

 Las propiedades que no tienen que especificarse necesariamente cuando se aplica el atributo se denominan "propiedades opcionales" (o "argumentos opcionales"). Se representan mediante propiedades que se pueden establecer. Los compiladores proporcionan una sintaxis especial para establecer estas propiedades cuando se aplica un atributo. Por ejemplo, la propiedad <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> representa un argumento opcional.

 ✔️ Asigne un nombre a las clases de atributos personalizados con el sufijo "Attribute".

 ✔️ Aplique el atributo <xref:System.AttributeUsageAttribute> a los atributos personalizados.

 ✔️ Proporcione propiedades que se pueden establecer para los argumentos opcionales.

 ✔️ Proporcione propiedades get-only para los argumentos requeridos.

 ✔️ Proporcione parámetros de constructor para inicializar las propiedades correspondientes a los argumentos necesarios. Cada parámetro debe tener el mismo nombre (aunque con distinto uso de mayúsculas y minúsculas) que la propiedad correspondiente.

 ❌ EVITE proporcionar parámetros de constructor para inicializar las propiedades correspondientes a los argumentos opcionales.

 En otras palabras, no tenga propiedades que se puedan establecer con un constructor y un establecedor. Esta instrucción consigue que resulte evidente qué argumentos son opcionales y cuáles necesarios, y evita tener dos formas de hacer lo mismo.

 ❌ EVITE sobrecargar los constructores de atributos personalizados.

 Tener un solo constructor comunica claramente al usuario qué argumentos son obligatorios y cuáles opcionales.

 ✔️ Selle las clases de atributos personalizados, si es posible. De esta forma, la búsqueda de atributos será más rápida.

 *Portions &copy; 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](index.md)
- [Instrucciones de uso](usage-guidelines.md)
