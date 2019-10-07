---
title: Procedimiento para determinar qué versiones de .NET Framework están instaladas
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abfa42be4b8c759da3fb34a2204058143e39689c
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2019
ms.locfileid: "71956666"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>Procedimiento para determinar qué versiones de .NET Framework están instaladas

Los usuarios pueden [instalar](https://docs.microsoft.com/dotnet/framework/install) y ejecutar varias versiones de .NET Framework en sus equipos. Al desarrollar o implementar una aplicación, puede que necesite conocer las versiones de .NET Framework que están instaladas en el equipo del usuario.

.NET Framework está formado por dos componentes principales con versiones separadas:

- Un conjunto de ensamblados, que son colecciones de tipos y recursos que proporcionan funciones a las aplicaciones. .NET Framework y los ensamblados comparten el mismo número de versión.

- Common Language Runtime (CLR), que administra y ejecuta el código de la aplicación. El CLR se identifica mediante su propio número de versión (consulte [Versiones y dependencias](versions-and-dependencies.md)).

> [!NOTE]
> Cada versión de .NET Framework contiene características de versiones anteriores e incorpora nuevas características. Puede cargar varias versiones de .NET Framework en un equipo al mismo tiempo, lo que significa que puede instalarlo sin tener que eliminar las versiones anteriores. En general, no debe desinstalar ninguna versión anterior de .NET Framework, ya que una determinada aplicación puede depender de una versión concreta y puede dejar de funcionar si se quita esa versión.
>
> Hay una diferencia entre la versión de .NET Framework y la versión de CLR:
>
> - Las versiones de .NET Framework se basan en el conjunto de ensamblados que conforman la biblioteca de clases .NET Framework. Por ejemplo, las versiones de .NET Framework incluyen 4.5, 4.6.1 y 4.7.2.
>- La versión de CLR se basa en el tiempo de ejecución en el que se ejecutan las aplicaciones de .NET Framework. Normalmente, una misma versión de CLR admite varias versiones de .NET Framework. Por ejemplo, la versión de CLR 4.0.30319.*xxxxx* admite las versiones de la 4 a la 4.5.2 de .NET Framework; donde *xxxxx* es inferior a 42000, y la versión de CLR 4.0.30319.42000 admite las versiones de .NET Framework a partir de .NET Framework 4.6.
>
> Para obtener más información sobre las versiones, vea [Versiones y dependencias de .NET Framework](versions-and-dependencies.md).

Para obtener una lista de las versiones de .NET Framework instaladas en un equipo, debe tener acceso al Registro. Puede usar el Editor del Registro para ver el Registro o usar código para consultarlo:

- Búsqueda de versiones más recientes de .NET Framework (4.5 y versiones posteriores):
  - [Uso del Editor del Registro para buscar versiones de .NET Framework](#net_b)
  - [Uso de código para consultar en el Registro las versiones de .NET Framework](#net_d)
  - [Uso de PowerShell para consultar en el Registro las versiones de .NET Framework](#ps_a)
- Búsqueda de versiones más antiguas de .NET Framework (1&#8211;4):
  - [Uso del Editor del Registro para buscar versiones de .NET Framework](#net_a)
  - [Uso de código para consultar en el Registro las versiones de .NET Framework](#net_c)

Para obtener una lista de las versiones de CLR instaladas en un equipo, use una herramienta o código:

- [Uso de la herramienta Clrver](#clr_a)
- [Uso de código para consultar la clase Environment](#clr_b)

Para obtener información sobre cómo detectar las actualizaciones instaladas de cada versión de .NET Framework, vea [Cómo: Determinar las actualizaciones de .NET Framework que están instaladas](how-to-determine-which-net-framework-updates-are-installed.md).

## <a name="find-newer-net-framework-versions-45-and-later"></a>Búsqueda de versiones más recientes de .NET Framework (4.5 y versiones posteriores)

<a name="net_b"></a>

### <a name="find-net-framework-versions-45-and-later-in-the-registry"></a>Búsqueda de las versiones de .NET Framework 4.5 y versiones posteriores en el Registro

1. En el menú **Inicio**, seleccione **Ejecutar**, escriba *regedit* y haga clic en **Aceptar**.

     Debe tener credenciales de administrador para ejecutar regedit.

2. En el Editor del Registro, abra la subclave siguiente: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**. Si la subclave **Full** no está presente, significa que .NET Framework 4.5 (o una versión posterior) no está instalado.

    > [!NOTE]
    > La carpeta **NET Framework Setup** del Registro *no* comienza con un punto.

3. Busque una entrada DWORD denominada **Release**. Si existe, significa que tiene instalado .NET Framework 4.5 o una versión posterior. Su valor es una clave de versión que corresponde a una versión concreta de .NET Framework. En la ilustración siguiente, por ejemplo, el valor de la entrada **Release** es *378389*, que es la clave de versión de .NET Framework 4.5.

     ![Entrada del Registro para .NET Framework 4.5](./media/clr-installdir.png "Registry entry for the .NET Framework 4.5")

En la tabla siguiente se muestra el valor de DWORD **Release** de sistemas operativos individuales para .NET Framework 4.5 y versiones posteriores.

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|Versión de .NET Framework|Valor DWORD de la versión|
|--------------------------------|-------------|
|.NET Framework 4.5|Todos los sistemas operativos Windows: 378389|
|.NET Framework 4.5.1|En Windows 8.1 y Windows Server 2012 R2: 378675<br />En todos los demás sistemas operativos Windows: 378758|
|.NET Framework 4.5.2|Todos los sistemas operativos Windows: 379893|
|.NET Framework 4.6|En Windows 10: 393295<br />En todos los demás sistemas operativos Windows: 393297|
|.NET Framework 4.6.1|En sistemas con la actualización de noviembre de Windows 10: 394254<br />En todos los demás sistemas operativos Windows (incluido Windows 10): 394271|
|.NET Framework 4.6.2|En la Actualización de aniversario de Windows 10 y Windows Server 2016: 394802<br />En todos los demás sistemas operativos Windows (incluidos otros sistemas operativos Windows 10): 394806|
|.NET Framework 4.7|En Windows 10 Creators Update: 460798<br />En todos los demás sistemas operativos Windows (incluidos otros sistemas operativos Windows 10): 460805|
|.NET Framework 4.7.1|En Windows 10 Fall Creators Update y Windows Server, versión 1709: 461308<br/>En todos los demás sistemas operativos Windows (incluidos otros sistemas operativos Windows 10): 461310|
|.NET Framework 4.7.2|En la actualización de Windows 10 de abril de 2018 y Windows Server, versión 1803: 461808<br/>En todos los sistemas operativos diferentes de la Actualización de abril de 2018 de Windows 10 y Windows Server, versión 1803: 461814|
|.NET Framework 4.8|En la actualización del 10 de mayo de 2019 de Windows 10: 528040<br/>En todos los demás sistemas operativos Windows (incluidos otros sistemas operativos Windows 10): 528049|

Puede usar estos valores de la manera siguiente:

- Para determinar si una versión específica de .NET Framework está instalada en una versión concreta del sistema operativo Windows, pruebe si el valor de DWORD **Release** es *igual al* valor que aparece en la tabla. Por ejemplo, para determinar si .NET Framework 4.6 está presente en un sistema Windows 10, pruebe un valor de **Release** que sea *igual a* 393295.

- Para determinar si existe una versión mínima de .NET Framework, utilice el valor más bajo de DWORD **Release** para dicha versión. Por ejemplo, si la aplicación se ejecuta en .NET Framework 4.6 o una versión posterior, pruebe un valor de DWORD **RELEASE** que sea *mayor o igual que* 393295. Para una tabla que muestra solo el valor mínimo de DWORD **RELEASE** para cada versión de .NET Framework, vea [Valores mínimos de DWORD Release para .NET Framework 4.5 y versiones posteriores](minimum-release-dword.md).

- Para probar varias versiones, empiece por probar un valor que sea *mayor o igual que* el valor más bajo de DWORD para la última versión de .NET Framework y, después, compare el valor con el valor más bajo de DWORD para cada versión anterior sucesiva. Por ejemplo, si la aplicación requiere .NET Framework 4.7 o versiones posteriores y quiere determinar cuál es la versión específica de .NET Framework existente, empiece por probar un valor de DWORD **RELEASE** que sea *mayor o igual que* 461808 (el valor de DWORD más pequeño para .NET Framework 4.7.2). Después, compare el valor de DWORD **RELEASE** con el valor más bajo de cada versión posterior de .NET Framework. Para una tabla que muestra solo el valor mínimo de DWORD **RELEASE** para cada versión de .NET Framework, vea [Valores mínimos de DWORD Release para .NET Framework 4.5 y versiones posteriores](minimum-release-dword.md).

<a name="net_d"></a>

### <a name="find-net-framework-versions-45-and-later-with-code"></a>Búsqueda de versiones de .NET Framework 4.5 y versiones posteriores con código

1. Use los métodos <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> y <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> para obtener acceso a la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** en el Registro de Windows.

    La existencia de la entrada DWORD **Release** en la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** indica que .NET Framework 4.5 (o una versión posterior) está instalado en un equipo.

2. Compruebe el valor de la entrada **Release** para determinar la versión instalada. Para que sea compatible con versiones posteriores, puede buscar un valor mayor o igual que el valor que se muestra en la [tabla de versiones de .NET Framework](#version_table).

En el ejemplo siguiente se comprueba el valor de la entrada **Release** del Registro para buscar .NET Framework 4.5 y las versiones posteriores que están instaladas:

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

Este ejemplo sigue la práctica recomendada para la comprobación de versión:

- Comprueba si el valor de la entrada **Release** es *mayor o igual* que el valor de las claves de versión conocidas.

- Realiza la comprobación en orden, desde la versión más reciente hasta la más antigua.

<a name="ps_a"></a>

### <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a>Búsqueda de una versión mínima requerida de .NET Framework (4.5 y posterior) con PowerShell

- Use comandos de PowerShell para comprobar el valor de la entrada **Release** de la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.

En los ejemplos siguientes se comprueba el valor de la entrada **Release** para determinar si está instalado .NET Framework 4.6.2 o una versión posterior. Este código devuelve `True` si está instalado y `False` en caso contrario.

```PowerShell
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

Para comprobar si hay una versión mínima requerida de .NET Framework diferente, reemplace *394802* en estos ejemplos por un valor **Release** de la [tabla de versiones de .NET Framework](#version_table).

## <a name="find-older-net-framework-versions-182114"></a>Búsqueda de versiones más antiguas de .NET Framework (1&#8211;4)

<a name="net_a"></a>

### <a name="find-net-framework-versions-182114-in-the-registry"></a>Búsqueda de versiones de 1 a 4 de .NET Framework en el Registro

1. En el menú **Inicio**, seleccione **Ejecutar**, escriba *regedit* y haga clic en **Aceptar**.

    Debe tener credenciales de administrador para ejecutar regedit.

2. En el Editor del Registro, abra la subclave siguiente: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:

    - Para las versiones de .NET Framework de 1.1 a 3.5, cada versión instalada aparece como una subclave bajo la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**. Por ejemplo, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**. El número de versión se almacena como un valor en la entrada **Version** de la subclave de versión.

    - Para .NET Framework 4, la entrada **Version** se halla bajo la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client**, bajo la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** o bajo ambas subclaves.

    > [!NOTE]
    > La carpeta **NET Framework Setup** del Registro no comienza con un punto.

    En la siguiente ilustración se muestra la subclave y su entrada **Version** para .NET Framework 3.5.

    ![Entrada del Registro de .NET Framework 3.5. ](./media/net-4-and-earlier.png ".NET Framework 3.5 y versiones anteriores")

<a name="net_c"></a>

### <a name="find-net-framework-versions-182114-with-code"></a>Búsqueda de versiones de .NET Framework de 1 a 4 con código

- Use la clase <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> para tener acceso a la subclave **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** en el Registro de Windows.

En el ejemplo siguiente se buscan las versiones de 1 a 4 de .NET Framework que están instaladas:

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a>Búsqueda de versiones de CLR

<a name="clr_a"></a>

### <a name="find-the-current-clr-version-with-clrverexe"></a>Búsqueda de la versión actual de CLR con Clrver.exe

Use la [herramienta de versión de CLR (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) para determinar qué versiones de CLR están instaladas en un equipo:

- En un [Símbolo del sistema para desarrolladores de Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs), escriba `clrver`.

    Salida de ejemplo:

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a>

### <a name="find-the-current-clr-version-with-the-environment-class"></a>Búsqueda de la versión actual de CLR con la clase Environment

> [!IMPORTANT]
> Para .NET Framework 4.5 y versiones posteriores, no use la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para detectar la versión de CLR. En su lugar, consultar el Registro como se describe en [Búsqueda de versiones de .NET Framework 4.5 y versiones posteriores con código](#net_d).

1. Consulte la propiedad <xref:System.Environment.Version?displayProperty=nameWithType> para recuperar un objeto <xref:System.Version>.

    El objeto `System.Version` devuelto identifica la versión de tiempo de ejecución que está ejecutando el código. No devuelve versiones de ensamblado ni otras versiones del runtime que se hayan instalado en el equipo.

    Para las versiones 4, 4.5, 4.5.1 y 4.5.2 de .NET Framework, la representación de cadena del objeto <xref:System.Version> devuelto tiene la forma 4.0.30319.*xxxxx*, donde *xxxxx* es inferior a 42000. Para .NET Framework 4.6 y versiones posteriores, tiene la forma 4.0.30319.42000.

2. Una vez que tenga el objeto `Version`, consúltelo de la manera siguiente:

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
