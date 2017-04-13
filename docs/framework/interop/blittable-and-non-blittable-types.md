---
title: "Blittable and Non-Blittable Types | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "interop marshaling, blittable types"
  - "blittable types, interop marshaling"
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
caps.latest.revision: 23
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 23
---
# Blittable and Non-Blittable Types
La mayor parte de los tipos de datos tienen una representación común en la memoria administrada y en la memoria no administrada, y no requieren un control especial por parte del contador de referencias interoperativo.  Estos tipos se denominan *tipos que pueden transferirse en bloque de bits* porque no requieren conversión cuando se pasan entre código administrado y código no administrado.  
  
 Las estructuras que se devuelven de llamadas de invocación de plataforma deben ser tipos que pueden transferirse en bloque de bits.  La invocación de plataforma no admite estructuras que no pueden transferirse en bloque de bits como tipos de valor devuelto.  
  
 Los siguientes tipos del espacio de nombres <xref:System> pueden transferirse en bloque de bits:  
  
-   <xref:System.Byte?displayProperty=fullName>  
  
-   <xref:System.SByte?displayProperty=fullName>  
  
-   <xref:System.Int16?displayProperty=fullName>  
  
-   <xref:System.UInt16?displayProperty=fullName>  
  
-   <xref:System.Int32?displayProperty=fullName>  
  
-   <xref:System.UInt32?displayProperty=fullName>  
  
-   <xref:System.Int64?displayProperty=fullName>  
  
-   <xref:System.UInt64?displayProperty=fullName>  
  
-   <xref:System.IntPtr?displayProperty=fullName>  
  
-   <xref:System.UIntPtr?displayProperty=fullName>  
  
-   <xref:System.Single?displayProperty=fullName>  
  
-   <xref:System.Double?displayProperty=fullName>  
  
 Los siguientes tipos complejos también pueden transferirse en bloque de bits:  
  
-   Matrices unidimensionales de tipos que pueden transferirse en bloque de bits, como una matriz de enteros.  Sin embargo, un tipo que contenga una matriz de variable de tipos que pueden transferirse en bloque de bits no se puede transferir en bloque de bits.  
  
-   Tipos de valor con formato que sólo contienen tipos que pueden transferirse en bloque de bits \(y clases si se realiza el cálculo de referencias como tipos con formato\).  Para obtener más información sobre los tipos de valor con formato, vea [Default Marshaling for Value Types](http://msdn.microsoft.com/es-es/4d9a876c-e05a-40ba-bd85-bd22877f984a).  
  
 Las referencias a objetos no pueden transferirse en bloque de bits.  Esto incluye una matriz de referencias a objetos que pueden transferirse en bloque de bits por sí mismos.  Por ejemplo, puede definir una estructura que puede transferirse en bloque de bits, pero no puede definir un tipo que puede transferirse en bloque de bits que contiene una matriz de referencias a dicha estructura.  
  
 Como medida de optimización, las matrices de tipos que pueden transferirse en bloque de bits y las clases que contienen solo miembros que pueden transferirse en bloque de bits se [anclan](../../../docs/framework/interop/copying-and-pinning.md) en lugar de copiarse durante el cálculo de referencias.  Puede parecer que se realiza el cálculo de referencias de estos tipos como parámetros In\/Out cuando el llamador y el destinatario de la llamada están en el mismo apartamento.  No obstante, el cálculo de referencias de estos tipos se realiza como parámetros In y el usuario debe aplicar los atributos <xref:System.Runtime.InteropServices.InAttribute> y <xref:System.Runtime.InteropServices.OutAttribute> si desea calcular la referencia del argumento como parámetro In\/Out.  
  
 Algunos tipos de datos administrados requieren una representación diferente en un entorno no administrado.  Estos tipos de datos que no pueden transferirse en bloque de bits se deben convertir a un formato cuyas referencias se puedan calcular.  Por ejemplo, las cadenas administradas son tipos que no pueden transferirse en bloque de bits porque deben convertirse en objetos de cadena antes de poder calcular las referencias.  
  
 En la tabla siguiente se enumeran tipos del espacio de nombres <xref:System> que no pueden transferirse en bloque de bits.  Los [delegados](http://msdn.microsoft.com/es-es/d176ee76-f982-494b-b03d-92e4118896e2), que son estructuras de datos que hacen referencia a un método estático o a una instancia de clase, tampoco pueden transferirse en bloque de bits.  
  
|Tipo que no puede transferirse en bloque de bits|Descripción|  
|------------------------------------------------------|-----------------|  
|[System.Array](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Se convierte en una matriz de estilo C o una matriz `SAFEARRAY`.|  
|[System.Boolean](http://msdn.microsoft.com/es-es/d4c00537-70f7-4ca6-8197-bfc1ec037ff9)|Se convierte en un valor de 1, 2 ó 4 bytes con `true` como 1 o \-1.|  
|[System.Char](http://msdn.microsoft.com/es-es/cecc87c1-075e-4cde-aa56-33d189f66feb)|Se convierte a un carácter Unicode o ANSI.|  
|[System.Class](http://msdn.microsoft.com/es-es/fe334af5-0123-43d8-be84-26f6f023ddb6)|Se convierte a una interfaz de clase.|  
|[System.Object](../../../docs/framework/interop/default-marshaling-for-objects.md)|Se convierte en una variante o interfaz.|  
|[System.Mdarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Se convierte en una matriz de estilo C o una matriz `SAFEARRAY`.|  
|[System.String](../../../docs/framework/interop/default-marshaling-for-strings.md)|Se convierte en una cadena que termina en una referencia nula o en BSTR.|  
|[System.Valuetype](http://msdn.microsoft.com/es-es/4d9a876c-e05a-40ba-bd85-bd22877f984a)|Se convierte en una estructura con una posición fija en memoria.|  
|[System.Szarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Se convierte en una matriz de estilo C o una matriz `SAFEARRAY`.|  
  
 Los tipos de clase y objeto se admiten sólo mediante interoperatividad COM.  Para obtener los tipos correspondientes en [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C\# y C\+\+, vea [Información general de la biblioteca de clases](../../../docs/standard/class-library-overview.md).  
  
## Vea también  
 [Default Marshaling Behavior](../../../docs/framework/interop/default-marshaling-behavior.md)