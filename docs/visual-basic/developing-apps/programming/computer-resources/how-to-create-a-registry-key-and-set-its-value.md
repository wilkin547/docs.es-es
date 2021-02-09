---
description: 'Más información acerca de: Procedimiento: para crear una clave del Registro y establecer su valor en Visual Basic'
title: Procedimiento para crear una clave del Registro y establecer su valor
ms.date: 07/20/2015
f1_keywords:
- RegistryKey.CreateSubKey
- RegistryKey.SetValue
helpviewer_keywords:
- registry keys [Visual Basic], creating
- registry [Visual Basic], adding values
- registry [Visual Basic], adding keys
- registry keys [Visual Basic], setting values
- examples [Visual Basic], registry
ms.assetid: d3e40f74-c283-480c-ab18-e5e9052cd814
ms.openlocfilehash: 73a6f5b2a092bb05df704fe6b9954ccbe13b5d90
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797736"
---
# <a name="how-to-create-a-registry-key-and-set-its-value-in-visual-basic"></a>Cómo: Crear una clave del Registro y establecer su valor en Visual Basic

El método `CreateSubKey` del objeto `My.Computer.Registry` se puede usar para crear una clave del Registro.

## <a name="procedure"></a>Procedimiento

### <a name="to-create-a-registry-key"></a>Para crear una clave del Registro

- Use el método `CreateSubKey`, especificando en qué subárbol se va a colocar la clave, así como el nombre de la clave. El parámetro `Subkey` no distingue entre mayúsculas y minúsculas. En este ejemplo se crea la clave del Registro `MyTestKey` en HKEY_CURRENT_USER.

    [!code-vb[VbResourceTasks#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#17)]

### <a name="to-create-a-registry-key-and-set-a-value-in-it"></a>Para crear una clave del Registro y establecer un valor en él

1. Use el método `CreateSubkey`, especificando en qué subárbol se va a colocar la clave, así como el nombre de la clave. En este ejemplo se crea la clave del Registro `MyTestKey` en HKEY_CURRENT_USER.

    [!code-vb[VbResourceTasks#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#17)]

2. Establezca el valor con el método `SetValue`. Este ejemplo establece el valor de la cadena. "MyTestKeyValue" en "This is a test value".

    [!code-vb[VbResourceTasks#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#14)]

## <a name="example"></a>Ejemplo

En este ejemplo se crea la clave del Registro `MyTestKey` en HKEY_CURRENT_USER y, después, establece el valor de la cadena `MyTestKeyValue` en `This is a test value`.

[!code-vb[VbResourceTasks#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#15)]

## <a name="robust-programming"></a>Programación sólida

Examine la estructura del Registro para buscar una ubicación adecuada para la clave. Por ejemplo, puede que quiera abrir la clave HKEY_CURRENT_USER\Software del usuario actual y crear una clave con el nombre de su empresa. Luego agregue los valores del Registro a la clave de la empresa.

Cuando se esté leyendo el Registro desde una aplicación Web, el usuario actual dependerá de la autenticación y suplantación implementadas en la aplicación Web.

Es más seguro escribir datos en la carpeta de usuario (<xref:Microsoft.Win32.Registry.CurrentUser>) que en el equipo local (<xref:Microsoft.Win32.Registry.LocalMachine>).

Cuando se crea un valor del Registro, se debe decidir qué hacer si ese valor ya existe. Puede que otro proceso, quizás uno malintencionado, ya haya creado el valor y tenga acceso a él. Al colocar datos en el valor del Registro, estos están a disposición del otro proceso. Para evitar esto, use el método <xref:Microsoft.Win32.RegistryKey.GetValue%2A>. Devuelve `Nothing` si la clave ya no existe.

Aunque la clave del Registro esté protegida por listas de control de acceso (ACL), no es seguro almacenar en ella datos secretos (por ejemplo, contraseñas) como texto sin formato.

Las condiciones siguientes pueden provocar una excepción:

- Que el nombre de la clave sea `Nothing` (<xref:System.ArgumentNullException>).

- Que el usuario no tenga permisos para crear claves del Registro (<xref:System.Security.SecurityException>).

- Que el nombre de la clave supere el límite de 255 caracteres (<xref:System.ArgumentException>).

- Que la clave esté cerrada (<xref:System.IO.IOException>).

- Que la clave del Registro sea de solo lectura (<xref:System.UnauthorizedAccessException>).

## <a name="net-framework-security"></a>Seguridad de .NET Framework

Para ejecutar este proceso, el ensamblado necesita un nivel de privilegio concedido por la clase <xref:System.Security.Permissions.RegistryPermission>. Si ejecuta el proceso en un contexto de confianza parcial, este podría desencadenar una excepción por falta de privilegios. De igual manera, el usuario debe tener las ACL correctas para crear o escribir en la configuración. Por ejemplo, una aplicación local que tenga permiso de seguridad de acceso del código puede que no tenga permiso para el sistema operativo. Para obtener más información, vea [Conceptos básicos sobre la seguridad de acceso del código](../../../../framework/misc/code-access-security-basics.md).

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A>
- <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A>
- [Leer y escribir en el Registro](reading-from-and-writing-to-the-registry.md)
- [Conceptos básicos sobre la seguridad de acceso del código](../../../../framework/misc/code-access-security-basics.md)
