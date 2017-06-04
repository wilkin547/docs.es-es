---
title: "Analizar cadenas en .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "analizar cadenas, acerca del análisis de cadenas"
  - "interfaz IFormatProvider, analizar cadenas"
  - "tipos base, analizar cadenas"
  - "Parse (método)"
  - "analizar cadenas"
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Analizar cadenas en .NET Framework
Una operación de análisis convierte una cadena que representa un tipo base de .NET Framework en ese tipo base.  Por ejemplo, una operación de análisis se usa para convertir una cadena en un número de punto flotante o en un valor de fecha y hora.  El método más usado para realizar una operación de análisis es el método `Parse`.  Como el análisis es la operación inversa a la de dar formato \(que implica convertir un tipo base en su representación de cadena\), se aplican muchas de las mismas reglas y convenciones.  De la misma manera que al dar formato se usa un objeto que implementa la interfaz <xref:System.IFormatProvider> para proporcionar información de formato correspondiente a la referencia cultural, el análisis también emplea un objeto que implementa la interfaz <xref:System.IFormatProvider> para determinar cómo interpretar una representación de cadena.  Para obtener más información, vea [Aplicar formato a tipos](../../../docs/standard/base-types/formatting-types.md).  
  
## En esta sección  
 [Analizar cadenas numéricas](../../../docs/standard/base-types/parsing-numeric.md)  
 Describe cómo se convierten cadenas en tipos numéricos de .NET Framework.  
  
 [Analizar cadenas de fecha y hora](../../../docs/standard/base-types/parsing-datetime.md)  
 Describe cómo se convierten cadenas en tipos **DateTime** de .NET Framework.  
  
 [Analizar otras cadenas](../../../docs/standard/base-types/parsing-other.md)  
 Describe cómo convertir cadenas en tipos **Char**, **Boolean** y **Enum**.  
  
## Secciones relacionadas  
 [Aplicar formato a tipos](../../../docs/standard/base-types/formatting-types.md)  
 Describe los conceptos básicos de formato, como especificadores de formato y proveedores de formato.  
  
 [Conversión de tipos en .NET Framework](../../../docs/standard/base-types/type-conversion.md)  
 Describe cómo se convierten los tipos.  
  
 [Tipos base](../../../docs/standard/base-types/index.md)  
 Describe las operaciones normales que se pueden realizar con tipos base de .NET Framework.