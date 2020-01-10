---
title: Operadores de igualdad
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
ms.openlocfilehash: 31a5ce18f4526b5e3b8411365dff812601de87ad
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709444"
---
# <a name="equality-operators"></a>Operadores de igualdad
En esta sección se describe la sobrecarga de los operadores de igualdad y se hace referencia a `operator==` y `operator!=` como operadores de igualdad.  
  
 **X DO NOT** uno de los operadores de igualdad y la otra sobrecarga.  
  
 **✓ DO** Asegúrese de que <xref:System.Object.Equals%2A?displayProperty=nameWithType> y los operadores de igualdad tienen exactamente la misma semántica y las características de rendimiento similares.  
  
 Esto suele significar que `Object.Equals` debe invalidarse cuando se sobrecargan los operadores de igualdad.  
  
 **X AVOID** iniciar excepciones desde los operadores de igualdad.  
  
 Por ejemplo, devuelve false si uno de los argumentos es null en lugar de producir `NullReferenceException`.  
  
## <a name="equality-operators-on-value-types"></a>Operadores de igualdad en tipos de valor  
 **✓ DO** sobrecargar los operadores de igualdad en los tipos de valor, si son iguales es significativo.  
  
 En la mayoría de los lenguajes de programación, no hay ninguna implementación predeterminada de `operator==` para los tipos de valor.  
  
## <a name="equality-operators-on-reference-types"></a>Operadores de igualdad en tipos de referencia  
 **X AVOID** sobrecargar operadores de igualdad de tipos de referencias mutables.  
  
 Muchos lenguajes tienen operadores de igualdad integrados para los tipos de referencia. Los operadores integrados normalmente implementan la igualdad de referencia y muchos desarrolladores se sorprenden cuando se cambia el comportamiento predeterminado a la igualdad de valores.  
  
 Este problema se mitiga en los tipos de referencia inmutables porque la inmutabilidad dificulta la diferencia entre la igualdad de referencia y la igualdad de valores.  
  
 **X AVOID** sobrecargar operadores de igualdad de tipos de referencia si la implementación sería mucho más lenta que el de igualdad de referencia.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
