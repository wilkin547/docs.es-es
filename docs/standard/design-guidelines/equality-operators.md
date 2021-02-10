---
description: 'Más información acerca de: Operadores de igualdad'
title: Operadores de igualdad
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
ms.openlocfilehash: 8678ed1b4bc320f685cf7ae172f064b3dededd04
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642245"
---
# <a name="equality-operators"></a>Operadores de igualdad

En esta sección se describe la sobrecarga de los operadores de igualdad y se hace referencia a `operator==` y `operator!=` como operadores de igualdad.

 ❌ NO sobrecargue uno de los operadores de igualdad y no el otro.

 ✔️ Asegúrese de que <xref:System.Object.Equals%2A?displayProperty=nameWithType> y los operadores de igualdad tienen exactamente la misma semántica y características de rendimiento similares.

 Esto suele significar que `Object.Equals` debe invalidarse cuando se sobrecargan los operadores de igualdad.

 ❌ EVITE generar excepciones desde operadores de igualdad.

 Por ejemplo, devuelva el valor false si uno de los argumentos es NULL en lugar de generar `NullReferenceException`.

## <a name="equality-operators-on-value-types"></a>Operadores de igualdad en tipos de valor

 ✔️ Sobrecargue los operadores de igualdad en los tipos de valor, si la igualdad es significativa.

 En la mayoría de los lenguajes de programación, no hay ninguna implementación predeterminada de `operator==` para los tipos de valor.

## <a name="equality-operators-on-reference-types"></a>Operadores de igualdad en tipos de referencia

 ❌ EVITE sobrecargar los operadores de igualdad en tipos de referencia mutables.

 Muchos lenguajes tienen operadores de igualdad integrados para los tipos de referencia. Los operadores integrados normalmente implementan la igualdad de referencia, y muchos desarrolladores se sorprenden cuando se cambia el comportamiento predeterminado a la igualdad de valores.

 Este problema se mitiga en los tipos de referencia inmutables porque la inmutabilidad dificulta la diferencia entre la igualdad de referencia y la igualdad de valores.

 ❌ EVITE sobrecargar los operadores de igualdad en los tipos de referencia si la implementación fuera significativamente más lenta que la de la igualdad de referencia.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](index.md)
- [Instrucciones de uso](usage-guidelines.md)
