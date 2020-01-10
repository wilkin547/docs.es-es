---
title: Convertir tipos de .NET Framework en cadenas
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
ms.openlocfilehash: a63e0175f6660967eb4aa678c6731d353e44e2d5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711082"
---
# <a name="converting-net-framework-types-to-strings"></a>Convertir tipos de .NET Framework en cadenas
Si desea convertir un tipo de .NET Framework en una cadena, utilice el método **ToString**. El método **ToString** devuelve una representación de cadena del tipo que se le pasa. En la tabla siguiente se enumeran los tipos de .NET Framework que devuelven una cadena en un formato que se asigna a las especificaciones de los esquemas XML (XSD).  
  
|Tipo de .NET Framework|Tipo de cadena devuelta|  
|-------------------------|--------------------------|  
|Booleano|"true", "false"|  
|Single.PositiveInfinity|"INF"|  
|Single.NegativeInfinity|"-INF"|  
|Double.PositiveInfinity|"INF"|  
|Double.NegativeInfinity|"-INF"|  
|DateTime|El formato es aaaa-MM-ddTHH:mm:sszzzzzz y sus subconjuntos.|  
|Timespan|El formato es PnYnMnTnHnMnS, por ejemplo, `P2Y10M15DT10H30M20S` corresponde a una duración de 2 años, 10 meses, 15 días, 10 horas, 30 minutos y 20 segundos.|  
  
## <a name="see-also"></a>Vea también

- [Conversión de tipos de datos XML](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)
- [Conversión de cadenas en tipos de datos de .NET Framework](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
