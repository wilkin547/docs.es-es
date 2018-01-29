---
title: "Cómo: Determinar qué versiones de .NET Framework están instaladas"
ms.date: 01/24/2018
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dd257e7d481a12389f8a47921ab985ca82a157fc
ms.sourcegitcommit: c3ebb11a66e85a465c9ba2c42592222630b7ff9e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>Cómo: Determinar qué versiones de .NET Framework están instaladas
Los usuarios pueden instalar y ejecutar varias versiones de .NET Framework en sus equipos. Al desarrollar o implementar una aplicación, puede que necesite conocer las versiones de .NET Framework que están instaladas en el equipo del usuario. .NET Framework está formado por dos componentes principales con versiones separadas:  
  
-   Un conjunto de ensamblados, que son colecciones de tipos y recursos que proporcionan funciones a las aplicaciones. .NET Framework y los ensamblados comparten el mismo número de versión.  
  
-   Common Language Runtime (CLR), que administra y ejecuta el código de la aplicación. El CLR se identifica mediante su propio número de versión (consulte [Versiones y dependencias](~/docs/framework/migration-guide/versions-and-dependencies.md)).  
  
 Para obtener una lista precisa de las versiones de .NET Framework instaladas en un equipo, visualice el Registro o consúltelo mediante código:  
  
 [Ver el Registro (versiones 1 a 4)](#net_a)  
 [Ver el Registro (versión 4.5 y posteriores)](#net_b)  
 [Consultar el Registro mediante código (versiones 1 a 4)](#net_c)  
 [Consultar el Registro mediante código (versión 4.5 y posteriores)](#net_d)  
 [Consultar el Registro mediante PowerShell (versión 4.5 y posteriores)](#ps_a)  
  
 Para identificar la versión de CRL puede usar una herramienta o código:  
  
 [Uso de la herramienta Clrver](#clr_a)  
 [Uso de código para consultar la clase System.Environment](#clr_b)  
  
 Para obtener información sobre cómo detectar las actualizaciones instaladas de cada versión de .NET Framework, vea [Cómo: Determinar qué actualizaciones de .NET Framework están instaladas](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md). Para obtener información sobre cómo instalar .NET Framework, consulte [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md) (Instalar .NET Framework para desarrolladores).  
  
<a name="net_a"></a>   
#### <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-1-4"></a>Para identificar las versiones de .NET Framework mediante la visualización del Registro (.NET Framework 1 a 4)  
  
1.  En el menú **Inicio**, elija **Ejecutar**.  
  
2.  En el cuadro **Abrir**, escriba **regedit.exe**.  
  
     Debe tener credenciales de administrador para ejecutar regedit.exe.  
  
3.  En el Editor del Registro, abra la subclave siguiente:  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     Las versiones instaladas se muestran bajo la subclave NDP. El número de versión se indica en la entrada **Versión**. En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la entrada **Versión** está en la subclave Client o Full (en NDP), o en ambas subclaves.  
  

    > [!NOTE]
    > La carpeta “NET Framework Setup” del Registro no comienza con un punto.

<a name="net_b"></a> 
#### <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-45-and-later"></a>Para identificar las versiones de .NET Framework mediante la visualización del Registro (.NET Framework 4.5 y posterior)

1. En el menú **Inicio**, elija **Ejecutar**.

2. En el cuadro **Abrir**, escriba **regedit.exe**.

     Debe tener credenciales de administrador para ejecutar regedit.exe.

3. En el Editor del Registro, abra la subclave siguiente:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     Tenga en cuenta que la ruta de acceso a la subclave `Full` incluye la subclave `Net Framework` en lugar de la `.NET Framework`.

    > [!NOTE]
    > Si la subclave `Full` no está presente, significa que .NET Framework 4.5 (o una versión posterior) no está instalado.

     Compruebe si existe un valor DWORD denominado `Release`. La existencia de un valor DWORD `Release` indica que en ese equipo está instalado [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o una versión anterior.

     ![Entrada del Registro para .NET Framework 4.5](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")

     El valor DWORD `Release` indica qué versión de .NET Framework está instalada.

    [!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

    |Valor DWORD de la versión|Versión|
    |--------------------------------|-------------|
    |378389|.NET Framework 4.5|
    |378675|.NET Framework 4.5.1 instalado con Windows 8.1 o Windows Server 2012 R2|
    |378758|.NET Framework 4.5.1 instalado en Windows 8, Windows 7 SP1 o Windows Vista SP2|
    |379893|.NET Framework 4.5.2|
    |En sistemas Windows 10: 393295<br /><br /> En las demás versiones de sistema operativo: 393297|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|
    |En sistemas con la actualización de noviembre de Windows 10: 394254<br /><br /> En las demás versiones del sistema operativo: 394271|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|
    |En la actualización de aniversario de Windows 10: 394802<br /><br /> En las demás versiones del sistema operativo: 394806|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]| 
    |En Windows 10 Creators Update: 460798<br/><br/> En las demás versiones de sistema operativo: 460805 | .NET Framework 4.7 |
    |En Windows 10 Fall Creators Update: 461308<br/><br/> En las demás versiones del sistema operativo: 461310 | .NET Framework 4.7.1 |
<a name="net_c"></a> 
#### <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-1-4"></a>Para identificar las versiones de .NET Framework con consultas en el Registro mediante código (.NET Framework 1 a 4)

- Utilice la clase <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> para tener acceso a la subclave Software\Microsoft\NET Framework Setup\NDP\ en HKEY_LOCAL_MACHINE en el Registro de Windows.

     El código siguiente ilustra un ejemplo de esta consulta.

    > [!NOTE]
    > En este código no se muestra cómo detectar [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o versiones posteriores. Compruebe el valor DWORD `Release` para detectar estas versiones, tal y como se describe en la sección anterior. Puede consultar el código que sí detecta [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o versiones posteriores en la sección siguiente de este artículo.

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

     El ejemplo genera un resultado similar al siguiente:

    ```
    v2.0.50727  2.0.50727.4016  SP2
    v3.0  3.0.30729.4037  SP2
    v3.5  3.5.30729.01  SP1
    v4
      Client  4.0.30319
      Full  4.0.30319
    ```

<a name="net_d"></a> 
#### <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-45-and-later"></a>Para identificar las versiones de .NET Framework con consultas en el Registro mediante código (.NET Framework 4.5 y posterior)

1. La existencia de un valor DWORD `Release` indica que ya se ha instalado .NET Framework 4.5 o posterior en un equipo. El valor de la palabra clave indica la versión instalada. Para comprobar esta palabra clave, use los métodos <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> y <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> de la clase <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> para obtener acceso a la subclave Software\Microsoft\NET Framework Setup\NDP\v4\Full, en HKEY_LOCAL_MACHINE, del Registro de Windows.

2. Compruebe el valor de la palabra clave `Release` para determinar la versión instalada. Para que sea compatible con el reenvío, puede buscar un valor mayor o igual que los valores que se muestran en la tabla. Estas son las versiones de .NET Framework y las palabras clave de `Release` asociadas.

    [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

    |Versión|Valor DWORD de la versión|
    |-------------|--------------------------------|
    |.NET Framework 4.5|378389|
    |.NET Framework 4.5.1 instalado con Windows 8.1|378675|
    |.NET Framework 4.5.1 instalado en Windows 8, Windows 7 SP1 o Windows Vista SP2|378758|
    |.NET Framework 4.5.2|379893|
    |.NET Framework 4.6 instalado con Windows 10|393295|
    |.NET Framework 4.6 instalado en las demás versiones del sistema operativo Windows|393297|
    |.NET Framework 4.6.1 instalado en Windows 10|394254|
    |.NET Framework 4.6.1 instalado en las demás versiones del sistema operativo Windows|394271|
    |.NET Framework 4.6.2 instalado en la Actualización de aniversario de Windows 10|394802|
    |.NET Framework 4.6.2 instalado en las demás versiones del sistema operativo Windows|394806|
    |.NET Framework 4.7 instalado en Windows 10 Creators Update|460798|
    |.NET Framework 4.7 instalado en las demás versiones del sistema operativo Windows|460805|
    |.NET Framework 4.7.1 instalado en Windows 10 Fall Creators Update|461308|
    |.NET Framework 4.7.1 instalado en las demás versiones del sistema operativo Windows|461310|

     El ejemplo siguiente comprueba el valor `Release` en el Registro para determinar si [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o una versión posterior de .NET Framework está instalada.

     [!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
     [!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

     Este ejemplo sigue la práctica recomendada para la comprobación de versión:

    - Comprueba si el valor de la entrada `Release` es *mayor o igual que* el valor de las claves conocidas de versión.

    - Realiza la comprobación en orden, desde la versión más reciente hasta la más antigua.

<a name="ps_a"></a> 
#### <a name="to-check-for-a-minimum-required-net-framework-version-by-querying-the-registry-in-powershell-net-framework-45-and-later"></a>Comprobación de una versión mínima requerida de .NET Framework realizando una consulta al registro en PowerShell (.NET Framework 4.5 y posteriores)

- En el ejemplo siguiente se comprueba el valor de la palabra clave `Release` para determinar si .NET Framework 4.6.2 o posterior está instalado, independientemente de la versión del sistema operativo Windows (se devolverá `True` si es así o `False` en caso contrario).

    ```PowerShell
    Get-ChildItem "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\" | Get-ItemPropertyValue -Name Release | ForEach-Object { $_ -ge 394802 } 
    ```

    Puede reemplazar `394802` en el ejemplo anterior con otro valor de la tabla siguiente para comprobar si hay otra versión de .NET Framework mínima requerida.
  
    |Versión|Valor mínimo de DWORD de la versión|
    |-------------|--------------------------------|
    |.NET Framework 4.5|378389|
    |.NET Framework 4.5.1|378675|
    |.NET Framework 4.5.2|379893|
    |[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|393295|
    |[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|394254|
    |[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]|394802|
    |.NET Framework 4.7|460798|
    |.NET Framework 4.7.1|461308|
    
<a name="clr_a"></a> 
#### <a name="to-find-the-current-runtime-version-by-using-the-clrver-tool"></a>Para identificar la versión de runtime actual mediante la herramienta Clrver

- Use la herramienta de versión de CLR (Clrver.exe) para determinar qué versiones de Common Language Runtime (CLR) están instaladas en un equipo.

     En un símbolo del sistema de Visual Studio, escriba `clrver`. Este comando produce un resultado similar al siguiente:

    ```
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

     Para obtener más información sobre el uso de esta herramienta, consulte [Clrver.exe (herramienta de versión de CLR)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).

<a name="clr_b"></a> 
#### <a name="to-find-the-current-runtime-version-by-querying-the-environment-class-in-code"></a>Para buscar la versión de runtime actual consultando la clase Environment en el código

- Consulte la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para recuperar un objeto <xref:System.Version> que identifique la versión de tiempo de ejecución que está ejecutando el código. Puede utilizar la propiedad <xref:System.Version.Major%2A?displayProperty=nameWithType> para obtener el identificador de versión principal (por ejemplo, "4" para la versión 4,0), la propiedad <xref:System.Version.Minor%2A?displayProperty=nameWithType> para obtener el identificador de versión secundaria (por ejemplo, "0" para la versión 4,0) o el método <xref:System.Object.ToString%2A?displayProperty=nameWithType> para obtener la cadena completa de la versión (por ejemplo, "4.0.30319.18010", como se muestra en el código siguiente). Esta propiedad devuelve un valor único que refleja la versión del runtime que está ejecutando el código actualmente; no devuelve versiones de ensamblado ni otras versiones del runtime que se hayan podido instalar en el equipo.

     Para las versiones 4, 4.5, 4.5.1 y 4.5.2 de .NET Framework, la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> devuelve un objeto <xref:System.Version> cuya representación de cadena tiene la forma `4.0.30319.xxxxx`. Para .NET Framework 4.6 y posterior, tiene la forma `4.0.30319.42000`.

    > [!IMPORTANT]
    > Para [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] y versiones posteriores, no se recomienda usar la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para detectar la versión del tiempo de ejecución. En su lugar, se recomienda consultar el Registro, como se describe en la sección anterior de este artículo [Para identificar las versiones de .NET Framework con consultas en el Registro mediante código (.NET Framework 4.5 y posterior)](#net_d).

     A continuación se muestra un ejemplo de cómo consultar la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para obtener información de la versión del runtime:

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

     El ejemplo genera un resultado similar al siguiente:

    ```
    Version: 4.0.30319.18010
    ```

## <a name="see-also"></a>Vea también
 [Determinar qué actualizaciones de .NET Framework están instaladas](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)  
 [Instalación de .NET Framework para desarrolladores](../../../docs/framework/install/guide-for-developers.md)  
 [Versiones y dependencias](~/docs/framework/migration-guide/versions-and-dependencies.md)
