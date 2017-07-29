---
title: La seguridad y el Registro (Visual Basic)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- security [Visual Basic], registry
- registry, security issues
ms.assetid: 9980aff7-2f69-492b-8f66-29a9a76d3df5
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2ca25e9ce82baf9d9f59ecd887aaf2cbb301f4e3
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="security-and-the-registry-visual-basic"></a>La seguridad y el Registro (Visual Basic)
En esta página se describen las implicaciones de seguridad relativas al almacenamiento de datos en el Registro.  
  
## <a name="permissions"></a>Permisos  
 Aunque la clave del Registro esté protegida por listas de control de acceso (ACL), no es seguro almacenar en ella datos secretos (por ejemplo, contraseñas) como texto sin formato.  
  
 Si trabaja con el Registro, puede poner en peligro la seguridad al permitir accesos inadecuados a recursos del sistema o a información protegida. Para usar estas propiedades, debe tener permisos de lectura y escritura de la enumeración <xref:System.Security.Permissions.RegistryPermissionAccess>, que controla el acceso a las variables del Registro. Cualquier código que se ejecute con plena confianza (bajo la directiva de seguridad predeterminada, cualquier código instalado en el disco duro local del usuario) tiene los permisos necesarios para tener acceso al Registro. Para obtener más información, consulte la clase <xref:System.Security.Permissions.RegistryPermission>.  
  
 No deben almacenarse variables de Registro en ubicaciones de memoria donde pueda obtener acceso el código sin <xref:System.Security.Permissions.RegistryPermission>. Igualmente, al conceder permisos, conceda también los privilegios mínimos necesarios para realizar el trabajo.  
  
 Los valores de acceso de permiso del Registro se definen mediante la enumeración <xref:System.Security.Permissions.RegistryPermissionAccess>. En la tabla siguiente se detallan sus miembros.  
  
|Valor|Acceso a las variables del Registro|  
|-----------|----------------------------------|  
|`AllAccess`|Creación, lectura y escritura|  
|`Create`|Crear|  
|`NoAccess`|Sin acceso|  
|`Read`|Leer|  
|`Write`|Write|  
  
## <a name="checking-values-in-registry-keys"></a>Comprobar valores en las claves del Registro  
 Cuando se crea un valor del Registro, se debe decidir qué hacer si ese valor ya existe. Puede que otro proceso, quizás uno malintencionado, ya haya creado el valor y tenga acceso a él. Al colocar datos en el valor del Registro, estos están a disposición del otro proceso. Para evitar esto, use el método `GetValue`. Devuelve `Nothing` si la clave ya no existe.  
  
> [!IMPORTANT]
>  Cuando se esté leyendo el Registro desde una aplicación Web, la identidad del usuario actual dependerá de la autenticación y suplantación implementadas en la aplicación Web.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 [Leer y escribir en el Registro](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)

