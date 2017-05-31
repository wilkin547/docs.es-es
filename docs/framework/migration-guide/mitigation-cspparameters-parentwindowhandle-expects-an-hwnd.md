---
title: "Mitigación: CspParameters.ParentWindowHandle espera HWND | Microsoft Docs"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- CspParameters.ParentWindowHandle
- CspParameters.ParentWindowHandle retargeting change
ms.assetid: 33264333-71d6-4d43-8827-9c98878cfea7
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 39e8e757a446b30ab18914465853138e1c239e40
ms.openlocfilehash: 31898c86adc687b63a1b7f02eee98aae9b16c5f7
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="mitigation-cspparametersparentwindowhandle-expects-an-hwnd"></a>Mitigación: CspParameters.ParentWindowHandle espera HWND

La propiedad <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A>, que se introdujo en .NET Framework 2.0, permite que una aplicación registre un valor de identificador de ventana principal, como que se abra cualquier interfaz de usuario necesaria para tener acceso a la clave (por ejemplo, la solicitud del PIN o un cuadro de diálogo de consentimiento) como elemento secundario modal de la ventana especificada. A partir de las aplicaciones orientadas a .NET Framework 4.7, un identificador de ventana (HWND) puede asignarse a esta propiedad.

En versiones de .NET Framework hasta .NET Framework 4.6.2, como valor asignado a la propiedad <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> se esperaba <xref:System.IntPtr>, que representa la ubicación de la memoria donde reside el valor del identificador de ventana. En Windows 7 y versiones anteriores del sistema operativo Windows, establecer la propiedad en `form.Handle` no tiene ningún efecto, pero en Windows 8 y versiones posteriores, da como resultado <xref:System.Security.Cryptography> con el mensaje "El parámetro no es correcto".

A partir de las aplicaciones que tienen como destino NET Framework 4.7, una aplicación de Windows Forms puede establecer la propiedad <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> con un código como el siguiente:

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="impact"></a>Impacto

Para las aplicaciones orientadas a .NET Framework 4.7 o versiones posteriores que desean registrar una relación de ventana principal, se recomienda usar la forma simplificada:

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="mitigation"></a>Mitigación

Los desarrolladores que habían identificado que el valor correcto era la dirección de la ubicación de memoria que mantiene el valor `form.Handle` pueden optar por este cambio de comportamiento si establecen el modificador <xref:System.Security.AppContext> `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` en `true`:

- Configurando mediante programación los modificadores de compatibilidad en la instancia <xref:System.Security.AppContext>.

- Agregando la siguiente línea a la sección `<runtime>` del archivo app.config:
   
   ```xml
   <runtime>
     <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
   </runtime>
   ```

En cambio, los usuarios que deseen optar por el nuevo comportamiento de las aplicaciones ejecutadas en .NET Framework 4.7 pero que están orientadas a una versión anterior de .NET Framework pueden establecer el modificador <xref:System.Security.AppContext> en `false`.
 
## <a name="see-also"></a>Vea también

[Cambios de redestinación en .NET Framework 4.7](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

