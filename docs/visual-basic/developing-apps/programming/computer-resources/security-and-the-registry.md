---
description: 'Más información acerca de: La seguridad y el Registro (Visual Basic)'
title: Seguridad y Registro
ms.date: 07/20/2015
helpviewer_keywords:
- security [Visual Basic], registry
- registry [Visual Basic], security issues
ms.assetid: 9980aff7-2f69-492b-8f66-29a9a76d3df5
ms.openlocfilehash: 2dc6413328bc32c004d281b096ee095d4f827feb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666386"
---
# <a name="security-and-the-registry-visual-basic"></a>La seguridad y el Registro (Visual Basic)

En esta página se describen las implicaciones de seguridad relativas al almacenamiento de datos en el Registro.  
  
## <a name="permissions"></a>Permisos  

 Aunque la clave del Registro esté protegida por listas de control de acceso (ACL), no es seguro almacenar en ella datos secretos (por ejemplo, contraseñas) como texto sin formato.  
  
 Si trabaja con el Registro, puede poner en peligro la seguridad al permitir accesos inadecuados a recursos del sistema o a información protegida. Para usar estas propiedades, debe tener permisos de lectura y escritura de la enumeración <xref:System.Security.Permissions.RegistryPermissionAccess>, que controla el acceso a las variables del Registro. Cualquier código que se ejecute con plena confianza (bajo la directiva de seguridad predeterminada, cualquier código instalado en el disco duro local del usuario) tiene los permisos necesarios para tener acceso al Registro. Para obtener más información, vea la clase <xref:System.Security.Permissions.RegistryPermission>.  
  
 No deben almacenarse variables de Registro en ubicaciones de memoria donde pueda obtener acceso el código sin <xref:System.Security.Permissions.RegistryPermission>. Igualmente, al conceder permisos, conceda también los privilegios mínimos necesarios para realizar el trabajo.  
  
 Los valores de acceso de permiso del Registro se definen mediante la enumeración <xref:System.Security.Permissions.RegistryPermissionAccess>. En la tabla siguiente se detallan sus miembros.  
  
|Value|Acceso a las variables del Registro|  
|-----------|----------------------------------|  
|`AllAccess`|Creación, lectura y escritura|  
|`Create`|Crear|  
|`NoAccess`|Sin acceso|  
|`Read`|Lectura|  
|`Write`|Escritura|  
  
## <a name="checking-values-in-registry-keys"></a>Comprobar valores en las claves del Registro  

 Cuando se crea un valor del Registro, se debe decidir qué hacer si ese valor ya existe. Puede que otro proceso, quizás uno malintencionado, ya haya creado el valor y tenga acceso a él. Al colocar datos en el valor del Registro, estos están a disposición del otro proceso. Para evitar esto, use el método `GetValue`. Devuelve `Nothing` si la clave ya no existe.  
  
> [!IMPORTANT]
> Cuando se esté leyendo el Registro desde una aplicación Web, la identidad del usuario actual dependerá de la autenticación y suplantación implementadas en la aplicación Web.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- [Leer y escribir en el Registro](reading-from-and-writing-to-the-registry.md)
