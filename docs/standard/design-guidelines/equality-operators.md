---
title: Operadores de igualdad
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27550a8fd8292029cad9c2e699374a190b1a532e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185641"
---
# <a name="equality-operators"></a>Operadores de igualdad
En esta sección se describe la sobrecarga de operadores de igualdad y hace referencia a `operator==` y `operator!=` como operadores de igualdad.  
  
 **X DO NOT** uno de los operadores de igualdad y la otra sobrecarga.  
  
 **✓ DO** Asegúrese de que <xref:System.Object.Equals%2A?displayProperty=nameWithType> y los operadores de igualdad tienen exactamente la misma semántica y las características de rendimiento similares.  
  
 Esto significa que a menudo `Object.Equals` debe invalidarse cuando se sobrecargan los operadores de igualdad.  
  
 **X AVOID** iniciar excepciones desde los operadores de igualdad.  
  
 Por ejemplo, devolver false si uno de los argumentos es null en lugar de producir `NullReferenceException`.  
  
## <a name="equality-operators-on-value-types"></a>Operadores de igualdad en los tipos de valor  
 **✓ DO** sobrecargar los operadores de igualdad en los tipos de valor, si son iguales es significativo.  
  
 En la mayoría de los lenguajes de programación, no hay ninguna implementación predeterminada de `operator==` para tipos de valor.  
  
## <a name="equality-operators-on-reference-types"></a>Operadores de igualdad con tipos de referencia  
 **X AVOID** sobrecargar operadores de igualdad de tipos de referencias mutables.  
  
 Muchos lenguajes tienen operadores de igualdad integrada para tipos de referencia. Los operadores integrados implementan generalmente la igualdad de referencia, y muchos desarrolladores se sorprenden cuando se cambia el comportamiento predeterminado para la igualdad de valor.  
  
 Este problema se mitiga para tipos de referencia inmutable porque inmutabilidad hace mucho más difícil Observe la diferencia entre la igualdad de referencia y la igualdad de valores.  
  
 **X AVOID** sobrecargar operadores de igualdad de tipos de referencia si la implementación sería mucho más lenta que el de igualdad de referencia.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
