---
ms.openlocfilehash: 8693c1fdef5fa194b16127d4f1dd87e23ad68f2d
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438053"
---
### <a name="casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception"></a>Excepción PlatformNotSupportedException al convertir un contenedor RCW en una interfaz de `InterfaceIsIInspectable`

Al convertir un contenedor RCW en una interfaz marcada como <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>, ahora se genera la excepción <xref:System.PlatformNotSupportedException>. Este cambio es una continuación de la [eliminación de la compatibilidad con WinRT de .NET](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).

#### <a name="version-introduced"></a>Versión introducida

5.0 RC2

#### <a name="change-description"></a>Descripción del cambio

En las versiones de .NET anteriores a la versión preliminar 6 de .NET 5.0, la conversión de un contenedor RCW en una interfaz marcada como <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> funcionaba según lo esperado. En las versiones preliminares 6 y 8 de NET 5.0 y RC1, se puede convertir correctamente un contenedor RCW en una interfaz de <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>. Sin embargo, es posible que incurra en infracciones de acceso al ejecutar métodos en la interfaz, ya que la compatibilidad subyacente en el entorno de ejecución [se ha eliminado en la versión preliminar 6 de .NET 5.0](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).

En .NET 5.0 RC2 y versiones posteriores, al convertir un contenedor RCW en una interfaz marcada como <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>, se generaba una excepción <xref:System.PlatformNotSupportedException> durante la conversión.

#### <a name="reason-for-change"></a>Motivo del cambio

La compatibilidad con <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> [se eliminó en una versión preliminar anterior de .NET 5.0](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net). Sin embargo, la conversión en una interfaz de <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> se pasó por alto debido a un error. Como la compatibilidad subyacente en el entorno de ejecución ya no existe, al generar una excepción <xref:System.PlatformNotSupportedException>, se habilita una ruta de error gradual. Al generar una excepción, también se puede detectar con más facilidad que esta característica ya no se admite.

#### <a name="recommended-action"></a>Acción recomendada

- Si puede definir la interfaz en un archivo de metadatos del entorno de ejecución de Windows (WinMD), use la herramienta C#/WinRT.

- De lo contrario, marque la interfaz como <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIUnknown> en lugar de <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> y, después, agregue tres entradas ficticias al inicio de la interfaz para los métodos de <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>. En el siguiente fragmento de código se muestra un ejemplo.

  ```csharp
  [InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
  interface IMine
  {
      // Do not call these three methods.
      // They're exclusively to fill in the slots in the vtable.
      void GetIIdsSlot();
      void GetRuntimeClassNameSlot();
      void GetTrustLevelSlot();

      // The original members of the IMine interface go here.
      ...
  }
  ```

#### <a name="category"></a>Categoría

Interop

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable?displayProperty=fullName>

<!--

#### Affected APIs

- `F:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable`

-->
