---
title: para determinar qué versiones de .NET Framework están instaladas
description: Use código, regedit.exe o PowerShell para detectar qué versiones de .NET Framework están instaladas en un equipo mediante una consulta al Registro de Windows.
ms.date: 02/03/2020
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
ms.openlocfilehash: 122441e9238fd91199aed255b0125f69081c0a8c
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990145"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>Procedimiento para determinar qué versiones de .NET Framework están instaladas

Los usuarios pueden [instalar](../install/index.md) y ejecutar varias versiones de .NET Framework en sus equipos. Al desarrollar o implementar una aplicación, puede que necesite conocer las versiones de .NET Framework que están instaladas en el equipo del usuario. El registro contiene una lista de las versiones de .NET Framework instaladas en un equipo.

.NET Framework está formado por dos componentes principales con versiones separadas:

- Un conjunto de ensamblados, que son colecciones de tipos y recursos que proporcionan funciones a las aplicaciones. .NET Framework y los ensamblados comparten el mismo número de versión. Por ejemplo, las versiones de .NET Framework incluyen 4.5, 4.6.1 y 4.7.2.

- Common Language Runtime (CLR), que administra y ejecuta el código de la aplicación. Normalmente, una misma versión de CLR admite varias versiones de .NET Framework. Por ejemplo, la versión de CLR 4.0.30319.*xxxxx* donde *xxxxx* es inferior a 42000, admite las versiones 4 a la 4.5.2 de .NET Framework. La versión de CLR mayor o igual que 4.0.30319.42000 admite las versiones de .NET Framework a partir de .NET Framework 4.6.

La comunidad ha creado herramientas que ayudan a detectar qué versiones de .NET Framework están instaladas:

- [https://github.com/jmalarcon/DotNetVersions](https://github.com/jmalarcon/DotNetVersions)

  Una línea de comandos de .NET 2.0.

- [https://github.com/EliteLoser/DotNetVersionLister](https://github.com/EliteLoser/DotNetVersionLister)

  Un módulo de PowerShell 2.0.

Para obtener información sobre cómo detectar las actualizaciones instaladas de cada versión de .NET Framework, vea [Cómo: Determinar las actualizaciones de .NET Framework que están instaladas](how-to-determine-which-net-framework-updates-are-installed.md).

## <a name="detect-net-framework-45-and-later-versions"></a>Detección de .NET Framework 4.5 y versiones posteriores

La versión de .NET Framework (4.5 y posteriores) instalada en un equipo se muestra en el Registro, en **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\V4\\Full**. Si falta la subclave **Full**, significa que .NET Framework 4.5 o superior no está instalado.

> [!NOTE]
> La carpeta **NET Framework Setup** del Registro *no* comienza con un punto.

El valor REG_DWORD de **Release** del Registro representa la versión de .NET Framework que está instalada.

<a name="version_table"></a>

| Versión de .NET Framework | Valor de **Release** |
| ---------------------- | -------------------------- |
| .NET Framework 4.5     | Todos los sistemas operativos Windows: 378389 |
| .NET Framework 4.5.1   | En Windows 8.1 y Windows Server 2012 R2: 378675<br />En todos los demás sistemas operativos Windows: 378758 |
| .NET Framework 4.5.2   | Todos los sistemas operativos Windows: 379893 |
| .NET Framework 4.6     | En Windows 10: 393295<br />En todos los demás sistemas operativos Windows: 393297 |
| .NET Framework 4.6.1   | En sistemas con la actualización de noviembre de Windows 10: 394254<br />En todos los demás sistemas operativos Windows (incluido Windows 10): 394271 |
| .NET Framework 4.6.2   | En la Actualización de aniversario de Windows 10 y Windows Server 2016: 394802<br />En todos los demás sistemas operativos Windows (incluidos otros sistemas operativos Windows 10): 394806 |
| .NET Framework 4.7     | En Windows 10 Creators Update: 460798<br />En todos los demás sistemas operativos Windows (incluidos otros sistemas operativos Windows 10): 460805 |
| .NET Framework 4.7.1   | En Windows 10 Fall Creators Update y Windows Server, versión 1709: 461308<br/>En todos los demás sistemas operativos Windows (incluidos otros sistemas operativos Windows 10): 461310 |
| .NET Framework 4.7.2   | En la actualización de Windows 10 de abril de 2018 y Windows Server, versión 1803: 461808<br/>En todos los sistemas operativos diferentes de la Actualización de abril de 2018 de Windows 10 y Windows Server, versión 1803: 461814 |
| .NET Framework 4.8     | En la actualización de Windows 10 de mayo de 2019 y en la de noviembre de 2019: 528040<br/>En la actualización de mayo de 2020 de Windows 10: 528372<br/>En todos los demás sistemas operativos Windows (incluidos otros sistemas operativos Windows 10): 528049 |

### <a name="minimum-version"></a>Versión mínima

Para determinar si existe una versión *mínima* de .NET Framework, use el valor más bajo de REG_DWORD de **Release** para esa versión de la tabla anterior.

Por ejemplo, si la aplicación se ejecuta en .NET Framework 4.8 o en una versión posterior, pruebe un valor de REG_DWORD de **Release** que sea *mayor o igual que* 528040.

| Versión de .NET Framework | Valor mínimo |
| ---------------------- | ------------- |
| .NET Framework 4.5     | 378389 |
| .NET Framework 4.5.1   | 378675 |
| .NET Framework 4.5.2   | 379893 |
| .NET Framework 4.6     | 393295 |
| .NET Framework 4.6.1   | 394254 |
| .NET Framework 4.6.2   | 394802 |
| .NET Framework 4.7     | 460798 |
| .NET Framework 4.7.1   | 461308 |
| .NET Framework 4.7.2   | 461808 |
| .NET Framework 4.8     | 528040 |

### <a name="use-registry-editor"></a>Uso del Editor del Registro

01. En el menú **Inicio**, seleccione **Ejecutar**, escriba *regedit* y haga clic en **Aceptar**.

    Debe tener credenciales de administrador para ejecutar regedit.

01. En el Editor del Registro, abra la subclave siguiente: **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**. Si la subclave **Full** no está presente, significa que .NET Framework 4.5 (o una versión posterior) no está instalado.

01. Busque una entrada REG_DWORD denominada **Release**. Si existe, significa que tiene instalado .NET Framework 4.5 o una versión posterior. Su valor corresponde a una versión concreta de .NET Framework. En la ilustración siguiente, por ejemplo, el valor de la entrada **Release** es 528040, que es la clave de versión de .NET Framework 4.8.

    ![Entrada del Registro para .NET Framework 4.5](./media/clr-installdir.png "Entrada del Registro para .NET Framework 4.5")

### <a name="use-powershell-to-check-for-a-minimum-version"></a>Uso de PowerShell para comprobar si hay una versión mínima

Use comandos de PowerShell para comprobar el valor de la entrada **Release** de la subclave **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**.

En los ejemplos siguientes se comprueba el valor de la entrada **Release** para determinar si está instalado .NET Framework 4.6.2 o una versión posterior. Este código devuelve `True` si está instalado y `False` en caso contrario.

```PowerShell
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

### <a name="query-the-registry-using-code"></a>Consulta del registro mediante código

01. Use los métodos <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> y <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> para acceder a la subclave **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full** en el Registro de Windows.

    > [!IMPORTANT]
    > Si la aplicación que está ejecutando es de 32 bits y se ejecuta en Windows de 64 bits, las rutas de acceso del Registro serán diferentes de las mostradas anteriormente. El registro de 64 bits está disponible en la subclave **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\** . Por ejemplo, la subclave del Registro para .NET Framework 4.5 es **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\NET Framework Setup\\NDP\\V4\\Full**.

01. Compruebe el valor REG_DWORD de **Release** para determinar la versión que está instalada. Para que sea compatible con versiones posteriores, puede buscar un valor mayor o igual que el valor que se muestra en la [tabla de versiones de .NET Framework](#version_table).

En el ejemplo siguiente se comprueba el valor de la entrada **Release** del Registro para buscar .NET Framework 4.5 y las versiones posteriores que están instaladas:

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

Este ejemplo sigue la práctica recomendada para la comprobación de versión:

- Comprueba si el valor de la entrada **Release** es *mayor o igual* que el valor de las claves de versión conocidas.
- Realiza la comprobación en orden, desde la versión más reciente hasta la más antigua.

## <a name="detect-net-framework-10-through-40"></a>Detección de .NET Framework 1.0 a 4.0

Cada versión de .NET Framework de 1.1 a 4.0 aparece como una subclave en **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP**. En la tabla siguiente se muestra la ruta de acceso a cada versión de .NET Framework. Para la mayoría de las versiones, hay un valor REG_DWORD de **Install** de `1` que indica que esta versión está instalada. En estas subclaves, hay también un valor REG_SZ de **Version** que contiene una cadena de versión.

> [!NOTE]
> La carpeta **NET Framework Setup** del Registro *no* comienza con un punto.

| Versión de Framework  | Subclave del Registro | Valor |
| ------------------ | --------------- | ----- |
| 1.0                | **HKLM\\Software\\Microsoft\\.NETFramework\\Policy\\v1.0\\3705**     | **Install** REG_SZ es igual a `1` |
| 1.1                | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v1.1.4322**   | **Install** REG_DWORD es igual a `1` |
| 2.0                | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v2.0.50727**  | **Install** REG_DWORD es igual a `1` |
| 3.0                | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v3.0\\Setup** | **InstallSuccess** REG_DWORD es igual a `1` |
| 3.5                | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v3.5**        | **Install** REG_DWORD es igual a `1` |
| 4.0 Client Profile | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v4\\Client**  | **Install** REG_DWORD es igual a `1` |
| 4.0 Full Profile   | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**    | **Install** REG_DWORD es igual a `1` |

> [!IMPORTANT]
> Si la aplicación que está ejecutando es de 32 bits y se ejecuta en Windows de 64 bits, las rutas de acceso del Registro serán diferentes de las mostradas anteriormente. El registro de 64 bits está disponible en la subclave **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\** . Por ejemplo, la subclave del Registro para .NET Framework 3.5 es **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\NET Framework Setup\\NDP\\v3.5**.

Tenga en cuenta que la ruta de acceso del registro a la subclave de .NET Framework 1.0 es diferente de la de los demás.

### <a name="use-registry-editor-older-framework-versions"></a>Uso del Editor del Registro (versiones anteriores de la plataforma)

01. En el menú **Inicio**, seleccione **Ejecutar**, escriba *regedit* y haga clic en **Aceptar**.

    Debe tener credenciales de administrador para ejecutar regedit.

01. Abra la subclave que coincida con la versión que desea comprobar. Use la tabla de la sección [Detección de .NET Framework 1.0 a 4.0](#detect-net-framework-10-through-40).

    En la siguiente ilustración se muestra la subclave y su valor de **Version** para .NET Framework 3.5.

    ![Entrada del registro para .NET Framework 3.5.](./media/net-4-and-earlier.png ".NET Framework 3.5 y versiones anteriores")

### <a name="query-the-registry-using-code-older-framework-versions"></a>Consultar el registro mediante código (versiones anteriores de la plataforma)

Use la clase <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> para acceder a la subclave **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP** en el Registro de Windows.

> [!IMPORTANT]
> Si la aplicación que está ejecutando es de 32 bits y se ejecuta en Windows de 64 bits, las rutas de acceso del Registro serán diferentes de las mostradas anteriormente. El registro de 64 bits está disponible en la subclave **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\** . Por ejemplo, la subclave del Registro para .NET Framework 3.5 es **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\NET Framework Setup\\NDP\\v3.5**.

En el ejemplo siguiente se buscan las versiones 1 a 4 de .NET Framework que están instaladas:

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a>Búsqueda de versiones de CLR

El CLR de .NET Framework que se instala con .NET Framework tiene versiones independientes. Hay dos maneras de detectar la versión del CLR de .NET Framework:

- **La herramienta Clrver.exe**

  Use la [herramienta de versión de CLR (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) para determinar qué versiones de CLR están instaladas en un equipo. Abra el [símbolo del sistema para desarrolladores de Visual Studio](../tools/developer-command-prompt-for-vs.md) y escriba `clrver`.

  Resultados del ejemplo:

  ```console
  Versions installed on the machine:
  v2.0.50727
  v4.0.30319
  ```

- **La clase `Environment`**

  > [!IMPORTANT]
  > Para .NET Framework 4.5 y versiones posteriores, no use la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para detectar la versión de CLR. En su lugar, consulte el Registro como se describe en [Detección de .NET Framework 4.5 y versiones posteriores](#detect-net-framework-45-and-later-versions).
  
  01. Consulte la propiedad <xref:System.Environment.Version?displayProperty=nameWithType> para recuperar un objeto <xref:System.Version>.
  
      El objeto `System.Version` devuelto identifica la versión de tiempo de ejecución que está ejecutando el código. No devuelve versiones de ensamblado ni otras versiones del runtime que se hayan instalado en el equipo.
  
      Para las versiones 4, 4.5, 4.5.1 y 4.5.2 de .NET Framework, la representación de cadena del objeto <xref:System.Version> devuelto tiene la forma 4.0.30319.*xxxxx*, donde *xxxxx* es inferior a 42000. Para .NET Framework 4.6 y versiones posteriores, tiene la forma 4.0.30319.42000.
  
  01. Una vez que tenga el objeto **Version**, consúltelo de la manera siguiente:
  
      - Para el identificador de versión principal (por ejemplo, *4* en la versión 4.0), use la propiedad <xref:System.Version.Major%2A?displayProperty=nameWithType>.
  
      - Para el identificador de versión secundaria (por ejemplo, *0* en la versión 4.0), use la propiedad <xref:System.Version.Minor%2A?displayProperty=nameWithType>.
  
      - Para la cadena de versión completa (por ejemplo, *4.0.30319.18010*), use el método <xref:System.Version.ToString%2A?displayProperty=nameWithType>. Este método devuelve un valor único que refleja la versión del runtime que está ejecutando el código. No devuelve versiones de ensamblado ni otras versiones del runtime que se hayan instalado en el equipo.

  En el ejemplo siguiente se usa la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para recuperar la información de la versión de CLR:
  
  [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
  [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a>Vea también

- [Cómo: Determinar las actualizaciones de .NET Framework que están instaladas](how-to-determine-which-net-framework-updates-are-installed.md)
- [Instalación de .NET Framework para desarrolladores](../install/guide-for-developers.md)
- [Versiones y dependencias de .NET Framework](versions-and-dependencies.md)
