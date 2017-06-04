---
title: "Security and On-the-Fly Code Generation | Microsoft Docs"
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
  - "code security, on-the-fly code generation"
  - "on-the-fly code generation"
  - "security [.NET Framework], on-the-fly code generation"
  - "secure coding, on-the-fly code generation"
ms.assetid: 6d221724-bb21-4d76-90c3-0ee2a2e69be2
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Security and On-the-Fly Code Generation
Algunas bibliotecas funcionan generando código y ejecutándolo para realizar algunas operaciones para el llamador.  El problema fundamental es generar código en nombre de código de menor confianza y ejecutarlo con una confianza superior.  El problema empeora cuando el llamador puede influir en la generación de código, por lo que debe asegurarse de generar solo código que considere seguro.  
  
 Necesitará saber exactamente qué código genera en todo momento.  Esto significa que debe tener controles estrictos sobre los valores que obtiene de un usuario, ya sean cadenas entre comillas \(que se deben escribir entre caracteres de escape para que no puedan incluir elementos de código imprevistos\), identificadores \(que se deben comprobar para verificar que son identificadores válidos\), o cualquier otra cosa.  Los identificadores pueden ser peligrosos porque un ensamblado compilado puede modificarse para que sus identificadores contengan caracteres extraños que probablemente lo interrumpirán \(aunque esta es una vulnerabilidad de seguridad muy poco frecuente\).  
  
 Es conveniente generar código con emisión de la reflexión porque suele ayudar a evitar muchos de estos problemas.  
  
 Al compilar el código, tenga en cuenta si hay alguna manera de que un programa malintencionado lo modifique.  ¿Existe algún momento, por breve que sea, durante el cual un código malintencionado puede cambiar el código fuente en el disco antes de que el compilador lo lea o antes de que el código cargue el archivo .dll?  Si es así, debe proteger el directorio que contiene estos archivos usando la seguridad de acceso del código o una lista de control de acceso en el sistema de archivos, según corresponda.  
  
 Si un llamador puede influir en el código generado de forma que se produzca un error del compilador, eso también podría suponer una vulnerabilidad de la seguridad.  
  
 Ejecute el código generado con la configuración de permisos más baja posible, usando <xref:System.Security.Permissions.SecurityAction> o [Deny](http://msdn.microsoft.com/es-es/6b4d2e01-c504-4ac3-b50e-d6f5e7f5df25).  
  
## Vea también  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)