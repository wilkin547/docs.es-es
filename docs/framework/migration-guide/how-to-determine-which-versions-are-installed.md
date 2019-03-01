---
title: Procedimiento para determinar qué versiones de .NET Framework están instaladas
ms.date: 02/20/2019
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
ms.openlocfilehash: d7661b3ebaa8f29d6d3b2adbc56c405c8f0945f3
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584179"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>Filtrar para determinar qué versiones de .NET Framework están instaladas

Los usuarios pueden instalar y ejecutar varias versiones de .NET Framework en sus equipos. Al desarrollar o implementar una aplicación, puede que necesite conocer las versiones de .NET Framework que están instaladas en el equipo del usuario. .NET Framework está formado por dos componentes principales con versiones separadas:  
  
- Un conjunto de ensamblados, que son colecciones de tipos y recursos que proporcionan funciones a las aplicaciones. .NET Framework y los ensamblados comparten el mismo número de versión.  
  
- Common Language Runtime (CLR), que administra y ejecuta el código de la aplicación. El CLR se identifica mediante su propio número de versión (consulte [Versiones y dependencias](~/docs/framework/migration-guide/versions-and-dependencies.md)).  
  
Para obtener una lista precisa de las versiones de .NET Framework instaladas en un equipo, visualice el Registro o consúltelo mediante código:  
  
 [Búsqueda de versiones 1 a 4 de .NET Framework en el Registro](#net_a)  
 [Búsqueda de versiones de .NET Framework 4.5 y versiones posteriores en el Registro](#net_b)  
 [Consultar el Registro mediante código (versiones 1 a 4)](#net_c)  
 [Consultar el Registro mediante código (versión 4.5 y posteriores)](#net_d)  
 [Consultar el Registro mediante PowerShell (versión 4.5 y posteriores)](#ps_a)  

 Para identificar la versión de CRL puede usar una herramienta o código:  
  
 [Uso de la herramienta Clrver](#clr_a)  
 [Uso de código para consultar la clase System.Environment](#clr_b)  

> [!NOTE]
> Hay una diferencia entre la versión de .NET Framework y la versión de Common Language Runtime (CLR). Las versiones de .NET Framework se basan en el conjunto de ensamblados que conforman la biblioteca de clases .NET Framework. Por ejemplo, las versiones de .NET Framework incluyen 4.5, 4.6.1 y 4.7.2. Las versiones de CLR se basan en el entorno de ejecución en el que se ejecutan las aplicaciones .NET Framework, y una única versión de CLR admite normalmente varias versiones de .NET Framework. La versión 4.30319 de CLR *xxxxx* admite las versiones 4 a 4.5.2 de .NET Framework ; la versión de CLR 4.30319.42000 admite las versiones de .NET Framework a partir de .NET Framework 4.6. Para obtener más información, vea la propiedad <xref:System.Environment.Version?displayProperty=nameWithType>.

 Para obtener información sobre cómo detectar las actualizaciones instaladas de cada versión de .NET Framework, vea [Cómo: Determinar qué actualizaciones de .NET Framework están instaladas](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md). Para obtener información sobre cómo instalar .NET Framework, consulte [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md) (Instalar .NET Framework para desarrolladores).  
  
<a name="net_a"></a>   
## <a name="find-net-framework-versions-1-4-in-the-registry"></a>Búsqueda de versiones 1 a 4 de .NET Framework en el Registro 
  
1.  En el menú **Inicio**, elija **Ejecutar**.  
  
2.  En el cuadro **Abrir**, escriba **regedit.exe**.  
  
     Debe tener credenciales de administrador para ejecutar regedit.exe.  
  
3.  En el Editor del Registro, abra la subclave siguiente:  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     Para las versiones 1.1 a 3.5 de .NET Framework, las versiones instaladas se muestran como subclaves en la subclave `NDP`. El número de versión se indica en la entrada **Version** de la subclave de versión. 
     
     En .NET Framework 4, la entrada **Version** se encuentra en la subclave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client`, en la subclave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full` o en ambas.

    > [!NOTE]
    > La carpeta “NET Framework Setup” del Registro no comienza con un punto.

    En la siguiente ilustración se muestra la subclave de .NET Framework 3.5, junto con su entrada **Version**.

     ![La entrada del Registro de .NET Framework 3.5. ](../../../docs/framework/migration-guide/media/net-4-and-earlier.png ".NET Framework 4 y versiones anteriores")

<a name="net_b"></a> 
## <a name="find-net-framework-versions-45-and-later-in-the-registry"></a>Búsqueda de las versiones de .NET Framework 4.5 y versiones posteriores en el Registro

1. En el menú **Inicio**, elija **Ejecutar**.

2. En el cuadro **Abrir**, escriba **regedit.exe**.

     Debe tener credenciales de administrador para ejecutar regedit.exe.

3. En el Editor del Registro, abra la subclave siguiente:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     Tenga en cuenta que la ruta de acceso a la subclave `Full` incluye la subclave `Net Framework` en lugar de la `.NET Framework`.

    > [!NOTE]
    > Si la subclave `Full` no está presente, significa que .NET Framework 4.5 (o una versión posterior) no está instalado.

     Compruebe si existe un valor DWORD denominado `Release`. La existencia del valor DWORD `Release` indica que ya se ha instalado .NET Framework 4.5 o posterior en ese equipo. Su valor es una clave de versión que corresponde a una versión concreta de .NET Framework. En la ilustración siguiente, por ejemplo, el valor DWORD `Release` es 378389, que es la clave de versión de .NET Framework 4.5. 

     ![Entrada del Registro para .NET Framework 4.5](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")

En la tabla siguiente se muestra el valor mínimo del valor DWORD `Release` para cada versión de .NET Framework. Puede usar estos valores de la manera siguiente:

- Para determinar si existe una versión mínima de .NET Framework, pruebe si el valor DWORD `Release` que se encuentra en el Registro es *mayor o igual que* el valor que aparece en la tabla. Por ejemplo, si la aplicación requiere .NET Framework 4.7 o versiones posteriores, probaría si el valor de versión mínimo es 460798.

- Para probar varias versiones, comience con la versión más reciente de .NET Framework y, luego, pruebe las versiones anteriores sucesivas.

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

|Versión de .NET Framework|Valor DWORD de la versión|
|--------------------------------|-------------|
|.NET Framework 4.5|378389|
|.NET Framework 4.5.1|378675|
|.NET Framework 4.5.2|379893|
|.NET Framework 4.6|393295|
|.NET Framework 4.6.1|394254|
|.NET Framework 4.6.2|394802|
|.NET Framework 4.7|460798|
|.NET Framework 4.7.1|461308|
|.NET Framework 4.7.2|461808|

Para obtener una tabla completa de claves de versión de .NET Framework para versiones específicas del sistema operativo Windows, consulte [.NET Framework release keys and Windows operating system versions](release-keys-and-os-versions.md) (Claves de versión de .NET Framework y versiones del sistema operativo Windows).

<a name="net_c"></a> 
## <a name="find-net-framework-versions-1-4-with-code"></a>Búsqueda de versiones de .NET Framework 1 a 4 con código

- Use la clase <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> para acceder a la subclave `Software\Microsoft\NET Framework Setup\NDP\` en la rama `HKEY_LOCAL_MACHINE` del Registro de Windows.

     El código siguiente ilustra un ejemplo de esta consulta.

    > [!NOTE]
    > Este código no muestra cómo detectar .NET Framework 4.5 o posterior. Compruebe el valor DWORD `Release` para detectar estas versiones, tal y como se describe en la sección anterior. Para información sobre el código que detecta .NET Framework 4.5 o versiones posteriores, consulte la sección siguiente de este artículo.

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

<a name="net_d"></a> 
## <a name="find-net-framework-versions-45-and-later-with-code"></a>Búsqueda de versiones de .NET Framework 4.5 y versiones posteriores con código

1. La existencia del valor DWORD `Release` en la clave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` indica que ya se ha instalado .NET Framework 4.5 o posterior en un equipo. El valor de la palabra clave indica la versión instalada. Para comprobar esta palabra clave, use los métodos <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> y <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> para acceder a la subclave del Registro de Windows.

2. Compruebe el valor de la palabra clave `Release` para determinar la versión instalada. Para ser compatible con el reenvío, puede buscar un valor mayor o igual que el valor que aparece en la tabla en la sección [Búsqueda de versiones de .NET Framework 4.5 y versiones posteriores en el Registro](#net_b).

En el ejemplo siguiente se comprueba el valor `Release` en el Registro para determinar si está instalado .NET Framework o una versión posterior.

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

Este ejemplo sigue la práctica recomendada para la comprobación de versión:

- Comprueba si el valor de la entrada `Release` es *mayor o igual que* el valor de las claves conocidas de versión.

- Realiza la comprobación en orden, desde la versión más reciente hasta la más antigua.

<a name="ps_a"></a> 
## <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a>Búsqueda de una versión mínima requerida de .NET Framework (4.5 y posterior) con PowerShell

En el ejemplo siguiente se comprueba el valor de la palabra clave `Release` para determinar si .NET Framework 4.6.2 o posterior está instalado (si lo está, se devuelve `True`; en caso contrario, `False`).

    ```PowerShell
    # PowerShell 5
    Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' | Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
    ```

    ```PowerShell
    # PowerShell 4
    (Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -gt 394802
    ```

    You can replace `394802` in the previous example with another value from the following table in the [Find .NET Framework versions 4.5 and later in the registry](#net_b) section to check for a different minimum required .NET Framework version.
  
<a name="clr_a"></a> 
## <a name="find-the-current-clr-version-with-clrverexe"></a>Búsqueda de la versión actual de CLR con Clrver.exe

Use la herramienta de versión de CLR (Clrver.exe) para determinar qué versiones de Common Language Runtime (CLR) están instaladas en un equipo.

En Símbolo del sistema para desarrolladores de Visual Studio, escriba `clrver`. Este comando produce un resultado similar al siguiente:

```console
Versions installed on the machine:
v2.0.50727
v4.0.30319
```

Para obtener más información sobre el uso de esta herramienta, consulte [Clrver.exe (herramienta de versión de CLR)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).

<a name="clr_b"></a> 
## <a name="find-the-current-clr-version-with-the-environment-class"></a>Búsqueda de la versión actual de CLR con la clase Environment

Puede recuperar el valor de la propiedad <xref:System.Environment.Version?displayProperty=nameWithType> para recuperar un objeto <xref:System.Version> que identifica la versión del entorno de ejecución que ejecuta actualmente el código. Esta propiedad devuelve un valor único que refleja la versión del entorno de ejecución que ejecuta actualmente el código; no devuelve versiones de ensamblado ni otras versiones del entorno de ejecución que se puedan haber instalado en el equipo. Puede usar la propiedad <xref:System.Version.Major%2A?displayProperty=nameWithType> para obtener el identificador de versión principal (por ejemplo, "4" para la versión 4.0), la propiedad <xref:System.Version.Minor%2A?displayProperty=nameWithType> para obtener el identificador de versión secundaria (por ejemplo, "0" para la versión 4.0) o el método <xref:System.Version.ToString%2A?displayProperty=nameWithType> para obtener la cadena de versión completa (por ejemplo, "4.0.30319.18010", tal como se muestra en el código siguiente). 

Para las versiones 4, 4.5, 4.5.1 y 4.5.2 de .NET Framework, la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> devuelve un objeto <xref:System.Version> cuya representación de cadena tiene la forma `4.0.30319.xxxxx`. Para .NET Framework 4.6 y posterior, tiene la forma `4.0.30319.42000`.

> [!IMPORTANT]
> Para .NET Framework 4.5 y versiones posteriores, no se recomienda usar la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para detectar la versión del entorno de ejecución. En su lugar, se recomienda consultar el Registro, como se describe en la sección anterior de este artículo [Para identificar las versiones de .NET Framework con consultas en el Registro mediante código (.NET Framework 4.5 y posterior)](#net_d).

En el ejemplo siguiente se usa la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para recuperar la información de la versión del entorno de ejecución:

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a>Vea también

- [Cómo: Determinar qué actualizaciones de .NET Framework están instaladas](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)
- [Instalación de .NET Framework para desarrolladores](../../../docs/framework/install/guide-for-developers.md)
- [Versiones y dependencias](~/docs/framework/migration-guide/versions-and-dependencies.md)
