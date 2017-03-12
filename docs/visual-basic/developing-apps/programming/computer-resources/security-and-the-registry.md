---
title: "La seguridad y el Registro (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Registro, temas de seguridad"
  - "seguridad [Visual Basic], Registro"
ms.assetid: 9980aff7-2f69-492b-8f66-29a9a76d3df5
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# La seguridad y el Registro (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Esta página describe las implicaciones de seguridad relativas al almacenamiento de datos en el Registro.  
  
## Permisos  
 Aunque la clave del Registro esté protegida por listas de control de acceso \(ACL\), no es seguro almacenar en ella datos secretos \(por ejemplo, contraseñas\) como texto sin formato.  
  
 Al trabajar con el Registro se puede comprometer la seguridad, al permitir accesos inadecuados a recursos del sistema o a información reservada.  Para utilizar estas propiedades, debe tener permisos de lectura y escritura de la enumeración <xref:System.Security.Permissions.RegistryPermissionAccess> que controla el acceso a las variables de Registro.  Cualquier código que se ejecute con plena confianza \(bajo la directiva de seguridad predeterminada, cualquier código instalado en el disco duro local del usuario\) tiene los permisos necesarios para tener acceso al Registro.  Para obtener más información, vea la clase <xref:System.Security.Permissions.RegistryPermission>.  
  
 No deben almacenarse variables de Registro en ubicaciones de memoria donde pueda obtener acceso el código sin <xref:System.Security.Permissions.RegistryPermission>.  Igualmente, al conceder permisos, conceda también los privilegios mínimos necesarios para realizar el trabajo.  
  
 La enumeración <xref:System.Security.Permissions.RegistryPermissionAccess> define los valores de acceso de permiso del Registro.  La siguiente tabla proporciona detalles de sus miembros.  
  
|Valor|Acceso a las variables del Registro|  
|-----------|-----------------------------------------|  
|`AllAccess`|Acceso de creación, lectura y escritura|  
|`Create`|Creación|  
|`NoAccess`|Sin acceso|  
|`Read`|Lectura|  
|`Write`|Escritura|  
  
## Comprobar valores en las claves del Registro  
 A la hora de crear valores de Registro, deberá decidir qué hacer si coinciden con otros ya existentes.  Es posible que otro proceso, probablemente malintencionado, haya creado el valor y tenga acceso a él.  Cuando ponga datos en el valor del Registro, los datos estarán disponibles para el otro proceso.  Para evitar esto, utilice el método `GetValue`.  Devuelve `Nothing` si la clave no existe ya.  
  
> [!IMPORTANT]
>  Cuando se esté leyendo el Registro desde una aplicación Web, la identidad del usuario actual dependerá de la autenticación y suplantación implementadas en la aplicación Web.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 [Leer y escribir en el Registro](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)