---
title: Información general sobre la seguridad de UI Automation
description: Lea información general sobre el modelo de seguridad para la automatización de la interfaz de usuario de Microsoft. Comprender el control de cuentas de usuario, las tareas que requieren más privilegios y archivos de manifiesto.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
ms.openlocfilehash: d483f282db8ce8e5653d6d83361fa44df05f63f5
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163140"
---
# <a name="ui-automation-security-overview"></a>Información general sobre la seguridad de UI Automation

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).

En esta información general se describe el modelo de seguridad de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] en Windows Vista.

<a name="User_Account_Control"></a>

## <a name="user-account-control"></a>Control de cuentas de usuario

La seguridad es un enfoque importante de Windows Vista y entre las innovaciones es la posibilidad de que los usuarios se ejecuten como usuarios estándar (no administradores) sin que sea necesario bloquear la ejecución de aplicaciones y servicios que requieran privilegios más altos.

En Windows Vista, la mayoría de las aplicaciones se proporcionan con un token estándar o administrativo. Si una aplicación no se puede identificar como aplicación administrativa, se inicia como aplicación estándar de forma predeterminada. Antes de que se pueda iniciar una aplicación identificada como administrativa, Windows Vista solicita al usuario su consentimiento para ejecutar la aplicación con privilegios elevados. La petición de consentimiento se muestra de forma predeterminada, aunque el usuario sea miembro del grupo de administradores local, porque los administradores ejecutan como usuarios estándar hasta que una aplicación o un componente del sistema que requiere credenciales administrativas solicita permiso para ejecutarse.

<a name="Tasks_Requiring_Higher_Privileges"></a>

## <a name="tasks-requiring-higher-privileges"></a>Tareas que requieren privilegios de mayor nivel

Cuando un usuario intenta realizar una tarea que requiere privilegios administrativos, Windows Vista muestra un cuadro de diálogo que pide al usuario que continúe. Este cuadro de diálogo está protegido contra la comunicación entre procesos, por lo que el software malintencionado no puede simular una entrada de usuario. De forma similar, la pantalla de inicio de sesión de escritorio normalmente no es accesible para otros procesos.

Los clientes de Automatización de la interfaz de usuario deben comunicarse con otros procesos, algunos de los cuales podrían ejecutarse con un nivel de privilegios superior. Los clientes también podrían necesitar acceder a los cuadros de diálogo del sistema que normalmente no son visibles para otros procesos. Por lo tanto, el sistema debe confiar en los clientes de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] y se deben ejecutar con privilegios especiales.

Para que las aplicaciones sean de confianza y poder comunicarse con aplicaciones que se ejecutan con un nivel de privilegios superior, deben estar firmadas.

<a name="Manifest_Files"></a>

## <a name="manifest-files"></a>Archivo de manifiesto

Para obtener acceso a la interfaz de usuario del sistema protegida, las aplicaciones deben compilarse con un archivo de manifiesto que incluya el `uiAccess` atributo en la `requestedExecutionLevel` etiqueta, como se indica a continuación:

```xml
<trustInfo xmlns="urn:schemas-microsoft-com:asm.v3">
  <security>
    <requestedPrivileges>
      <requestedExecutionLevel
        level="highestAvailable"
        uiAccess="true" />
    </requestedPrivileges>
  </security>
</trustInfo>
```

El valor del atributo `level` en este código es solo un ejemplo.

`uiAccess`es "false" de forma predeterminada; es decir, si se omite el atributo o si no hay ningún manifiesto para el ensamblado, la aplicación no podrá obtener acceso a la interfaz de usuario protegida.
