---
title: "Creating a Cryptographic Scheme | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "encryption [.NET Framework], creating cryptographic schemes"
  - "cryptography [.NET Framework], creating cryptographic schemes"
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Creating a Cryptographic Scheme
Los componentes criptográficos de .NET Framework se pueden combinar para crear distintos esquemas para cifrar y descifrar datos.  
  
 Un esquema criptográfico simple para cifrar y descifrar datos podría especificar los siguientes pasos:  
  
1.  Cada parte genera un par de claves pública y privada.  
  
2.  Las partes intercambian sus claves públicas.  
  
3.  Cada parte genera una clave secreta para el cifrado TripleDES, por ejemplo, y cifra la clave recién creada con la clave pública de la otra parte.  
  
4.  Una parte envía los datos a la otra y combina la clave secreta de la otra con la suya propia en un determinado orden para crear una nueva clave secreta.  
  
5.  Después, las partes inician una conversación mediante el cifrado simétrico.  
  
 Crear un esquema criptográfico no es una tarea trivial.  Para obtener más información sobre el uso de la criptografía, consulte el tema Criptografía en la documentación de Platform SDK en http:\/\/msdn.microsoft.com\/library.  
  
## Vea también  
 [Servicios criptográficos](../../../docs/standard/security/cryptographic-services.md)