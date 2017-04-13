---
title: "C&#243;mo: Determinar qu&#233; versiones de .NET Framework est&#225;n instaladas | Microsoft Docs"
ms.custom: ""
ms.date: "04/07/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework, determinar la versión"
  - "versiones, determinar para .NET Framework"
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
caps.latest.revision: 62
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 53
---
# C&#243;mo: Determinar qu&#233; versiones de .NET Framework est&#225;n instaladas
Los usuarios pueden instalar y ejecutar varias versiones de .NET Framework en sus equipos. Al desarrollar o implementar una aplicación, puede que necesite conocer las versiones de .NET Framework que están instaladas en el equipo del usuario. .NET Framework está formado por dos componentes principales con versiones separadas:  
  
-   Un conjunto de ensamblados, que son colecciones de tipos y recursos que proporcionan funciones a las aplicaciones. .NET Framework y los ensamblados comparten el mismo número de versión.  
  
-   Common Language Runtime \(CLR\), que administra y ejecuta el código de la aplicación. La plataforma CLR se identifica mediante su propio número de versión \(consulte [Versiones y dependencias](../../../docs/framework/migration-guide/versions-and-dependencies.md)\).  
  
 Para obtener una lista precisa de las versiones de .NET Framework instaladas en un equipo, visualice el Registro o consúltelo mediante código:  
  
 [Consultar el registro \(versiones 1 a 4\)](#net_a)  
[Consultar el registro \(versión 4.5 y posteriores\)](#net_b)  
[Consultar el registro mediante el código \(versiones 1 a 4\)](#net_c)  
[Consultar el registro mediante el código \(versión 4.5 y posteriores\)](#net_d)  
  
 Para identificar la versión de CRL puede usar una herramienta o código:  
  
 [Uso de la herramienta Clrver](#clr_a)  
[Uso del código para consultar la clase System.Environment](#clr_b)  
  
 Para obtener más información sobre cómo detectar las actualizaciones instaladas de cada versión de .NET Framework, consulte [Cómo: Determinar qué actualizaciones de .NET Framework están instaladas](../../../docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md). Para obtener información acerca de la instalación de .NET Framework, vea la [guía de instalación](../../../docs/framework/install/guide-for-developers.md).  
  
<a name="net_a"></a>   
#### Para identificar las versiones de .NET Framework mediante la visualización del Registro \(.NET Framework 1 a 4\)  
  
1.  En el menú **Inicio**, elija **Ejecutar**.  
  
2.  En el cuadro **Abrir**, escriba **regedit.exe**.  
  
     Debe tener credenciales de administrador para ejecutar regedit.exe.  
  
3.  En el Editor del Registro, abra la subclave siguiente:  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     Las versiones instaladas se muestran bajo la subclave NDP. El número de versión se indica en la entrada **Version**. En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la entrada **Version** está en la subclave Client o Full \(en NDP\), o en ambas subclaves.  
  
    > [!NOTE]
    >  La carpeta “NET Framework Setup” del Registro no comienza con un punto.  
  
<a name="net_b"></a>   
#### Para identificar las versiones de .NET Framework mediante la visualización del Registro \(.NET Framework 4.5 y posterior\)  
  
1.  En el menú **Inicio**, elija **Ejecutar**.  
  
2.  En el cuadro **Abrir**, escriba **regedit.exe**.  
  
     Debe tener credenciales de administrador para ejecutar regedit.exe.  
  
3.  En el Editor del Registro, abra la subclave siguiente:  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`  
  
     Tenga en cuenta que la ruta de acceso a la subclave `Full` incluye la subclave `Net Framework` en lugar de la `.NET Framework`.  
  
    > [!NOTE]
    >  Si la subclave `Full` no está presente, significa que .NET Framework 4.5 \(o una versión posterior\) no está instalado.  
  
     Compruebe si existe un valor DWORD denominado `Release`. La existencia de un valor DWORD `Release` indica que en ese equipo está instalado [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o una versión anterior.  
  
     ![Entrada del Registro para .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR\_InstallDir")  
  
     El valor DWORD `Release` indica qué versión de .NET Framework está instalada.  
  
    |Valor DWORD de la versión|Versión|  
    |-------------------------------|-------------|  
    |378389|.NET Framework 4.5|  
    |378675|.NET Framework 4.5.1 instalado con Windows 8.1 o Windows Server 2012 R2|  
    |378758|.NET Framework 4.5.1 instalado en Windows 8, Windows 7 SP1 o Windows Vista SP2|  
    |379893|.NET Framework 4.5.2|  
    |En sistemas Windows 10: 393295<br /><br /> En las demás versiones de sistema operativo: 393297|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|  
    |En sistemas con la actualización de noviembre de Windows 10: 394254<br /><br /> En las demás versiones del sistema operativo: 394271|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|  
  
<a name="net_c"></a>   
#### Para identificar las versiones de .NET Framework con consultas en el Registro mediante código \(.NET Framework 1 a 4\)  
  
-   Use la clase <xref:Microsoft.Win32.RegistryKey?displayProperty=fullName> para obtener acceso a la subclave Software\\Microsoft\\NET Framework Setup\\NDP\\ que se encuentra en HKEY\_LOCAL\_MACHINE en el Registro de Windows.  
  
     El código siguiente ilustra un ejemplo de esta consulta.  
  
    > [!NOTE]
    >  En este código no se muestra cómo detectar [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o versiones posteriores. Compruebe el valor DWORD `Release` para detectar estas versiones, tal y como se describe en la sección anterior.  
  
     [!code-csharp[ListVersions#0](../../../samples/snippets/csharp/VS_Snippets_CLR/listversions/cs/program.cs#0)]
     [!code-vb[ListVersions#0](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listversions/vb/program.vb#0)]  
    [!code-csharp[ListVersions#1](../../../samples/snippets/csharp/VS_Snippets_CLR/listversions/cs/program.cs#1)]
    [!code-vb[ListVersions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listversions/vb/program.vb#1)]  
  
     El ejemplo genera un resultado similar al siguiente:  
  
    ```  
  
    v2.0.50727  2.0.50727.4016  SP2 v3.0  3.0.30729.4037  SP2 v3.5  3.5.30729.01  SP1 v4 Client  4.0.30319 Full  4.0.30319  
    ```  
  
<a name="net_d"></a>   
#### Para identificar las versiones de .NET Framework con consultas en el Registro mediante código \(.NET Framework 4.5 y posterior\)  
  
1.  La existencia de un valor DWORD `Release` indica que ya se ha instalado .NET Framework 4.5 o posterior en un equipo. El valor de la palabra clave indica la versión instalada. Para comprobar esta palabra clave, use los métodos <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> y <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> de la clase <xref:Microsoft.Win32.RegistryKey?displayProperty=fullName> para acceder a la subclave Software\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full en HKEY\_LOCAL\_MACHINE, en el Registro de Windows.  
  
2.  Compruebe el valor de la palabra clave `Release` para determinar la versión instalada. Para que sea compatible con el reenvío, puede buscar un valor mayor o igual que los valores que se muestran en la tabla. Estas son las versiones de .NET Framework y las palabras clave de `Release` asociadas.  
  
    |Versión|Valor DWORD de la versión|  
    |-------------|-------------------------------|  
    |.NET Framework 4.5|378389|  
    |.NET Framework 4.5.1 instalado con Windows 8.1|378675|  
    |.NET Framework 4.5.1 instalado en Windows 8, Windows 7 SP1 o Windows Vista SP2|378758|  
    |.NET Framework 4.5.2|379893|  
    |[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] instalado con Windows 10|393295|  
    |[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] instalado en las demás versiones del sistema operativo Windows|393297|  
    |[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] instalado en Windows 10|394254|  
    |[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] instalado en las demás versiones del sistema operativo Windows|394271|  
  
     Este es un ejemplo de comprobación de un valor mayor o igual que los valores de palabra clave de la versión para cada versión:  
  
     [!code-csharp[ListVersions#0](../../../samples/snippets/csharp/VS_Snippets_CLR/listversions/cs/program.cs#0)]
     [!code-vb[ListVersions#0](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listversions/vb/program.vb#0)]  
    [!code-csharp[ListVersions#3](../../../samples/snippets/csharp/VS_Snippets_CLR/listversions/cs/program.cs#3)]
    [!code-vb[ListVersions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listversions/vb/program.vb#3)]  
    [!code-csharp[ListVersions#4](../../../samples/snippets/csharp/VS_Snippets_CLR/listversions/cs/program.cs#4)]
    [!code-vb[ListVersions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listversions/vb/program.vb#4)]  
  
     El ejemplo genera un resultado similar al siguiente:  
  
    ```  
    Version: 4.5.1 or later  
    ```  
  
<a name="clr_a"></a>   
#### Para identificar la versión de runtime actual mediante la herramienta Clrver  
  
-   Use la herramienta de versión de CLR \(Clrver.exe\) para determinar qué versiones de Common Language Runtime \(CLR\) están instaladas en un equipo.  
  
     En un símbolo del sistema de Visual Studio, escriba `clrver`. Este comando produce un resultado similar al siguiente:  
  
    ```  
    Versions installed on the machine: v2.0.50727 v4.0.30319  
    ```  
  
     Para obtener más información sobre el uso de esta herramienta, consulte [Clrver.exe \(CLR Version Tool\)](../../../docs/framework/tools/clrver-exe-clr-version-tool.md).  
  
<a name="clr_b"></a>   
#### Para buscar la versión de runtime actual consultando la clase Environment en el código  
  
-   Consulte la propiedad <xref:System.Environment.Version%2A?displayProperty=fullName> para recuperar un objeto <xref:System.Version> que identifique la versión de tiempo de ejecución que está ejecutando el código. Puede utilizar la propiedad <xref:System.Version.Major%2A?displayProperty=fullName> para obtener el identificador de versión principal \(por ejemplo, "4" para la versión 4,0\), la propiedad <xref:System.Version.Minor%2A?displayProperty=fullName> para obtener el identificador de versión secundaria \(por ejemplo, "0" para la versión 4,0\) o el método <xref:System.Object.ToString%2A?displayProperty=fullName> para obtener la cadena completa de la versión \(por ejemplo, "4.0.30319.18010", como se muestra en el código siguiente\). Esta propiedad devuelve un valor único que refleja la versión del runtime que está ejecutando el código actualmente; no devuelve versiones de ensamblado ni otras versiones del runtime que se hayan podido instalar en el equipo.  
  
     Para las versiones 4, 4.5, 4.5.1 y 4.5.2 de .NET Framework, la propiedad <xref:System.Environment.Version%2A?displayProperty=fullName> devuelve un objeto <xref:System.Version> cuya representación de cadena tiene la forma `4.0.30319.xxxxx`. Para [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], tiene la forma `4.0.30319.42000`.  
  
     A continuación se muestra un ejemplo de cómo consultar la propiedad <xref:System.Environment.Version%2A?displayProperty=fullName> para obtener información de la versión del runtime:  
  
     [!code-csharp[ListVersions#0](../../../samples/snippets/csharp/VS_Snippets_CLR/listversions/cs/program.cs#0)]
     [!code-vb[ListVersions#0](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listversions/vb/program.vb#0)]  
    [!code-csharp[ListVersions#2](../../../samples/snippets/csharp/VS_Snippets_CLR/listversions/cs/program.cs#2)]
    [!code-vb[ListVersions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listversions/vb/program.vb#2)]  
  
     El ejemplo genera un resultado similar al siguiente:  
  
    ```  
    Version: 4.0.30319.18010  
    ```  
  
## Vea también  
 [Cómo: Determinar qué actualizaciones de .NET Framework están instaladas](../../../docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)   
 [Guía de instalación](../../../docs/framework/install/guide-for-developers.md)   
 [Versiones y dependencias](../../../docs/framework/migration-guide/versions-and-dependencies.md)