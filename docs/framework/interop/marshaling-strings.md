---
title: "Marshaling Strings | Microsoft Docs"
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
  - "marshaling, samples"
  - "platform invoke, marshaling data"
  - "data marshaling, strings"
  - "data marshaling, samples"
  - "data marshaling, platform invoke"
  - "marshaling. strings"
  - "marshaling, platform invoke"
  - "sample applications [.NET Framework], marshaling strings"
ms.assetid: e21b078b-70fb-4905-be26-c097ab2433ff
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Marshaling Strings
En la invocación de plataforma se copian los parámetros de cadena y se convierten del formato de .NET Framework \(Unicode\) al formato no administrado \(ANSI\), si se requiere.  Como las cadenas administradas son inmutables, en la invocación de plataforma no se vuelven a copiar desde la memoria no administrada a la memoria administrada cuando finaliza la función.  
  
 En la tabla siguiente se enumeran las opciones de cálculo de referencias para las cadenas, se describe su uso y se proporciona un vínculo al ejemplo correspondiente en .NET Framework.  
  
|Cadena.|Descripción|Ejemplo|  
|-------------|-----------------|-------------|  
|Por valor|Pasa las cadenas como parámetros In.|[MsgBox](../../../docs/framework/interop/msgbox-sample.md)|  
|Como resultado|Devuelve las cadenas desde el código no administrado.|[Cadenas](http://msdn.microsoft.com/es-es/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|Por referencia|Pasa las cadenas como parámetros In\/Out mediante <xref:System.Text.StringBuilder>.|[Buffers](http://msdn.microsoft.com/es-es/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5)|  
|En una estructura por valor|Pasa las cadenas en una estructura que es un parámetro In.|[Structs](http://msdn.microsoft.com/es-es/96a62265-dcf9-4608-bc0a-1f762ab9f48e)|  
|En una estructura por referencia **\(char\*\)**|Pasa las cadenas en una estructura que es un parámetro In\/Out.  La función no administrada espera recibir un puntero a un búfer de caracteres y el tamaño del búfer es un miembro de la estructura.|[Cadenas](http://msdn.microsoft.com/es-es/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|En una estructura por referencia **\(char\[\]\)**|Pasa las cadenas en una estructura que es un parámetro In\/Out.  La función no administrada espera recibir un búfer de caracteres incrustado.|[OSInfo](http://msdn.microsoft.com/es-es/69d89067-507b-41fe-859d-30bf3ff29455)|  
|En una clase por valor **\(char\*\)**|Pasa las cadenas en una clase \(una clase es un parámetro In\/Out\).  La función no administrada espera recibir un puntero a un búfer de caracteres.|[OpenFileDlg](http://msdn.microsoft.com/es-es/b7dea792-cb92-4baf-ac7b-6a24803e6c75)|  
|En una clase por valor **\(char\[\]\)**|Pasa las cadenas en una clase \(una clase es un parámetro In\/Out\).  La función no administrada espera recibir un búfer de caracteres incrustado.|[OSInfo](http://msdn.microsoft.com/es-es/69d89067-507b-41fe-859d-30bf3ff29455)|  
|Como una matriz de cadenas por valor|Crea una matriz de cadenas que se pasa por valor.|[Matrices](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
|Como una matriz de estructuras que contienen cadenas por valor|Crea una matriz de estructuras que contienen cadenas y la matriz se pasa por valor.|[Matrices](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
  
## Vea también  
 [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)   
 [Platform Invoke Data Types](http://msdn.microsoft.com/es-es/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [Marshaling Classes, Structures, and Unions](../../../docs/framework/interop/marshaling-classes-structures-and-unions.md)   
 [Marshaling Arrays of Types](http://msdn.microsoft.com/es-es/049b1c1b-228f-4445-88ec-91bc7fd4b1e8)   
 [Miscellaneous Marshaling Samples](http://msdn.microsoft.com/es-es/a915c948-54e9-4d0f-a525-95a77fd8ed70)