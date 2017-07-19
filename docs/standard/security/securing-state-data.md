---
title: "Securing State Data | Microsoft Docs"
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
  - "security [.NET Framework], state data"
  - "code security, state data"
  - "secure coding, state data"
  - "state data security"
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Securing State Data
En las aplicaciones en las que se tratan datos confidenciales o en las que se toma cualquier tipo de decisión sobre la seguridad, es necesario mantener los datos bajo control y no permitir que un posible código malintencionado tenga acceso directo a los datos.  La mejor forma de proteger los datos en la memoria consiste en declarar los datos como variables privadas o internas \(con el ámbito limitado al mismo ensamblado\).  No obstante, incluso estos datos están expuestos al acceso malintencionado, por tanto, deberá tener en cuenta lo siguiente:  
  
-   Utilizar mecanismos de reflexión, el código de alta confianza que puede hacer referencia al objeto puede obtener y establecer miembros privados.  
  
-   Utilizar la serialización, el código de alta confianza puede obtener y establecer miembros privados de forma eficaz si puede tener acceso a los datos correspondientes en el formulario serializado del objeto.  
  
-   Estos datos se pueden leer durante la depuración.  
  
 Compruebe que ninguno de sus métodos o propiedades expone estos valores involuntariamente.  
  
 En algunos casos, los datos se pueden declarar como "protegidos", con acceso limitado a la clase y sus derivados.  No obstante, se deben tomar las siguientes precauciones adicionales debido a una mayor exposición:  
  
-   Controlar los códigos a los que se permite derivar de la clase mediante la restricción del código al mismo ensamblado o la seguridad declarativa, que se describe en [Proteger acceso a métodos](../../../docs/framework/misc/securing-method-access.md), con el fin de que sea necesario alguna identidad o permisos para que el código se derive de la clase.  
  
-   Asegurarse de que en todas las clases derivadas se implementa una protección similar o que estén selladas.  
  
## Vea también  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)