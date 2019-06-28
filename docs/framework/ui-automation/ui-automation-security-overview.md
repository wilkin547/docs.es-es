---
title: Información general sobre la seguridad de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
ms.openlocfilehash: c74f770f917fc3b2a7d3a18c08270745dac68b12
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422426"
---
# <a name="ui-automation-security-overview"></a>Información general sobre la seguridad de UI Automation

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).

Esta información general describe el modelo de seguridad de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] en [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)].

<a name="User_Account_Control"></a>

## <a name="user-account-control"></a>Control de cuentas de usuario

La seguridad es un aspecto muy importante de [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] y una de las innovaciones es la posibilidad de que los usuarios ejecuten como usuarios estándar (no administrador) sin que necesariamente se les impida ejecutar aplicaciones y servicios que requieren privilegios más altos.

En [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)], la mayoría de las aplicaciones se proporcionan con un token estándar o un token administrativo. Si una aplicación no se puede identificar como aplicación administrativa, se inicia como aplicación estándar de forma predeterminada. Para poder iniciar una aplicación identificada como administrativa, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] pide al usuario su consentimiento para ejecutar la aplicación con privilegios elevados. La petición de consentimiento se muestra de forma predeterminada, aunque el usuario sea miembro del grupo de administradores local, porque los administradores ejecutan como usuarios estándar hasta que una aplicación o un componente del sistema que requiere credenciales administrativas solicita permiso para ejecutarse.

<a name="Tasks_Requiring_Higher_Privileges"></a>

## <a name="tasks-requiring-higher-privileges"></a>Tareas que requieren privilegios de mayor nivel

Cuando un usuario intenta realizar una tarea que requiere privilegios administrativos, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] presenta un cuadro de diálogo que pide al usuario su consentimiento para continuar. Este cuadro de diálogo está protegido contra la comunicación entre procesos, por lo que el software malintencionado no puede simular una entrada de usuario. De forma similar, la pantalla de inicio de sesión de escritorio normalmente no es accesible para otros procesos.

Los clientes de Automatización de la interfaz de usuario deben comunicarse con otros procesos, algunos de los cuales podrían ejecutarse con un nivel de privilegios superior. Los clientes también podrían necesitar acceder a los cuadros de diálogo del sistema que normalmente no son visibles para otros procesos. Por lo tanto, el sistema debe confiar en los clientes de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] y se deben ejecutar con privilegios especiales.

Para que las aplicaciones sean de confianza y poder comunicarse con aplicaciones que se ejecutan con un nivel de privilegios superior, deben estar firmadas.

<a name="Manifest_Files"></a>

## <a name="manifest-files"></a>Archivo de manifiesto

Para obtener acceso a la interfaz de usuario protegidos del sistema, las aplicaciones deben compilarse con un archivo de manifiesto que incluye el `uiAccess` atributo en la `requestedExecutionLevel` etiqueta, como se indica a continuación:

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

`uiAccess` es "false" de forma predeterminada; es decir, si se omite el atributo, o si no hay ningún manifiesto del ensamblado, la aplicación no pueda obtener acceso a la interfaz de usuario protegido.

Para obtener más información sobre [!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)] seguridad, sobre cómo firmar aplicaciones y sobre la creación de manifiestos de ensamblado, vea [Developer Best Practices and Guidelines for Applications en un entorno con menos privilegios](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480150(v=msdn.10)).
