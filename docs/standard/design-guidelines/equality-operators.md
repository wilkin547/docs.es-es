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
ms.openlocfilehash: 5b1e5784de277d59c7bc945cbe7b605653eec7bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571022"
---
# <a name="equality-operators"></a>Operadores de igualdad
En esta sección se describe la sobrecarga de operadores de igualdad y hace referencia a `operator==` y `operator!=` como operadores de igualdad.  
  
 **X DO NOT** uno de los operadores de igualdad y la otra sobrecarga.  
  
 **✓ DO** Asegúrese de que <xref:System.Object.Equals%2A?displayProperty=nameWithType> y los operadores de igualdad tienen exactamente la misma semántica y las características de rendimiento similares.  
  
 Esto significa que a menudo `Object.Equals` debe reemplazarse cuando se sobrecargan los operadores de igualdad.  
  
 **X AVOID** iniciar excepciones desde los operadores de igualdad.  
  
 Por ejemplo, devolver false si uno de los argumentos es null en lugar de producir `NullReferenceException`.  
  
## <a name="equality-operators-on-value-types"></a>Operadores de igualdad en los tipos de valor  
 **✓ DO** sobrecargar los operadores de igualdad en los tipos de valor, si son iguales es significativo.  
  
 En la mayoría de los lenguajes de programación, no hay ninguna implementación predeterminada de `operator==` para tipos de valor.  
  
## <a name="equality-operators-on-reference-types"></a>Operadores de igualdad de tipos de referencia  
 **X AVOID** sobrecargar operadores de igualdad de tipos de referencias mutables.  
  
 Muchos lenguajes tienen operadores de igualdad integrados para tipos de referencia. Los operadores integrados implementan generalmente la igualdad de referencia, y muchos desarrolladores se sorprenda cuando se cambia el comportamiento predeterminado para la igualdad de valor.  
  
 Este problema se mitiga para tipos de referencia inmutable porque inmutabilidad resulta mucho más complejo debe tener en cuenta la diferencia entre la igualdad de referencia y la igualdad de valor.  
  
 **X AVOID** sobrecargar operadores de igualdad de tipos de referencia si la implementación sería mucho más lenta que el de igualdad de referencia.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
