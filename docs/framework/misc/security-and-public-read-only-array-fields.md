---
title: "Security and Public Read-only Array Fields | Microsoft Docs"
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
  - "security [.NET Framework], public read-only array fields"
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Security and Public Read-only Array Fields
No utilice nunca los campos de matriz públicos de sólo lectura de las bibliotecas administradas para definir el comportamiento del límite o la seguridad de las aplicaciones porque dichos campos pueden modificarse.  
  
## Comentarios  
 Algunas clases de .NET Framework incluyen campos públicos de sólo lectura que contienen parámetros de límite específicos de la plataforma.  Por ejemplo, el campo <xref:System.IO.Path.InvalidPathChars> es una matriz que describe los caracteres no permitidos en una cadena de ruta de acceso a un archivo.  En .NET Framework existen muchos campos similares.  
  
 Su código o el código que comparte el dominio de aplicación de su código puede modificar los valores de los campos de sólo lectura públicos tales como <xref:System.IO.Path.InvalidPathChars>.  No debe utilizar campos de matriz públicos de sólo lectura como éste para definir el comportamiento del límite de sus aplicaciones.  Si lo hace, el código malintencionado podrá modificar las definiciones del límite y utilizar su código de manera inesperada.  
  
 En la versión 2.0 y posteriores de .NET Framework, debe utilizar métodos que devuelvan una nueva matriz en lugar de usar campos de matriz públicos.  Por ejemplo, en lugar de utilizar el campo <xref:System.IO.Path.InvalidPathChars>, deberá utilizar el método <xref:System.IO.Path.GetInvalidPathChars%2A>.  
  
 Observe que los tipos de .NET Framework no utilizan campos públicos para definir tipos de límites internamente.  En lugar de ello, .NET Framework utiliza campos privados separados.  Si se cambian los valores de estos campos públicos, no se modifica el comportamiento de los tipos de .NET Framework.  
  
## Vea también  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)