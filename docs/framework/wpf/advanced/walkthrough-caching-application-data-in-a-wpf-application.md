---
title: "Tutorial: Almacenar en caché datos de la aplicación en una aplicación de WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81d808b982852d5cc6dc187a3c8389748a0dc0bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a>Tutorial: Almacenar en caché datos de la aplicación en una aplicación de WPF
El almacenamiento en caché permite almacenar datos en memoria para un acceso rápido. Cuando se tiene acceso a los datos de nuevo, las aplicaciones puedan obtener los datos de la memoria caché en su lugar la recuperación de la fuente original. Esto puede mejorar el rendimiento y la escalabilidad. Además, el almacenamiento en caché permite que los datos estén disponibles cuando el origen de datos no está disponible temporalmente.  
  
 El [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporciona clases que le permiten usar el almacenamiento en caché en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] aplicaciones. Estas clases se encuentran en el <xref:System.Runtime.Caching> espacio de nombres.  
  
> [!NOTE]
>  El <xref:System.Runtime.Caching> espacio de nombres es nuevo en el [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]. Este espacio de nombres facilita el almacenamiento en caché está disponible para todos los [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] las aplicaciones. En versiones anteriores de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], el almacenamiento en caché solo estaba disponible en el espacio de nombres <xref:System.Web> y, por tanto, exigía una dependencia en las clases de ASP.NET.  
  
 En este tutorial se muestra cómo utilizar la funcionalidad de almacenamiento en caché que está disponible en la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] como parte de una [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicación. En el tutorial, almacenar en caché el contenido de un archivo de texto.  
  
 Las tareas que se ilustran en este tutorial son las siguientes:  
  
-   Crear un proyecto de aplicación de WPF.  
  
-   Agregar una referencia a la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
-   Inicializar una memoria caché.  
  
-   Agregar una entrada de caché que contiene el contenido de un archivo de texto.  
  
-   Proporcionar una directiva de expulsión de la entrada de caché.  
  
-   Supervisión de la ruta de acceso del archivo almacenado en caché y avisa de la instancia de la memoria caché cambia a los elementos supervisados.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Microsoft [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   Un archivo de texto que contiene una pequeña cantidad de texto. (Se mostrará el contenido del archivo de texto en un cuadro de mensaje). El código que se muestra en el tutorial se da por supuesto que está trabajando con el archivo siguiente:  
  
     `c:\cache\cacheText.txt`  
  
     Sin embargo, puede usar cualquier archivo de texto y realizar pequeños cambios en el código de este tutorial.  
  
## <a name="creating-a-wpf-application-project"></a>Crear un proyecto de aplicación de WPF  
 Para empezar a crear un proyecto de aplicación de WPF.  
  
#### <a name="to-create-a-wpf-application"></a>Para crear una aplicación WPF  
  
1.  Inicie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
2.  En el **archivo** menú, haga clic en **New**y, a continuación, haga clic en **nuevo proyecto**.  
  
     Aparecerá el cuadro de diálogo **Nuevo proyecto**.  
  
3.  En **plantillas instaladas**, seleccione el lenguaje de programación que desea utilizar (**Visual Basic** o **Visual C#**).  
  
4.  En el **nuevo proyecto** cuadro de diálogo, seleccione **aplicación WPF**.  
  
    > [!NOTE]
    >  Si no ve el **aplicación WPF** plantilla, asegúrese de que tiene como destino una versión de la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que admita WPF. En el **nuevo proyecto** cuadro de diálogo, seleccione [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] en la lista.  
  
5.  En el **nombre** texto cuadro, escriba un nombre para el proyecto. Por ejemplo, puede escribir **WPFCaching**.  
  
6.  Seleccione el **crear directorio para la solución** casilla de verificación.  
  
7.  Haga clic en **Aceptar**.  
  
     Se abre el Diseñador de WPF en **diseño** ver y muestra el archivo MainWindow.xaml. [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]crea el **mi proyecto** carpeta, el archivo Application.xaml y el archivo MainWindow.xaml.  
  
## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a>.NET Framework de destino y agregue una referencia a los ensamblados de almacenamiento en caché  
 De forma predeterminada, el destino de las aplicaciones de WPF el [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]. Para usar el <xref:System.Runtime.Caching> espacio de nombres en una aplicación WPF, la aplicación debe tener como destino el [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (no el [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) y debe incluir una referencia al espacio de nombres.  
  
 Por lo tanto, el paso siguiente es cambiar el destino de .NET Framework y agregar una referencia a la <xref:System.Runtime.Caching> espacio de nombres.  
  
> [!NOTE]
>  El procedimiento para cambiar el destino de .NET Framework es diferente en un proyecto de Visual Basic y en un proyecto de Visual C#.  
  
#### <a name="to-change-the-target-net-framework-in-visual-basic"></a>Para cambiar el destino de .NET Framework en Visual Basic  
  
1.  En **el Explorador de soluciones**, haga clic en el nombre del proyecto y, a continuación, haga clic en **propiedades**.  
  
     Se muestra la ventana Propiedades de la aplicación.  
  
2.  Haga clic en la pestaña **Compilar**.  
  
3.  En la parte inferior de la ventana, haga clic en **opciones de compilación avanzadas...** .  
  
     El **configuración de compilador avanzada** se muestra el cuadro de diálogo.  
  
4.  En el **.NET framework de destino (todas las configuraciones)** lista, seleccione [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]. (No seleccione [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)  
  
5.  Haga clic en **Aceptar**.  
  
     El **cambio de plataforma de destino** se muestra el cuadro de diálogo.  
  
6.  En el **cambio de plataforma de destino** cuadro de diálogo, haga clic en **Sí**.  
  
     El proyecto se cierra y, a continuación, se vuelve a abrir.  
  
7.  Agregue una referencia al ensamblado de almacenamiento en caché siguiendo estos pasos:  
  
    1.  En **el Explorador de soluciones**, haga clic en el nombre del proyecto y, a continuación, haga clic en **Agregar referencia**.  
  
    2.  Seleccione el **.NET** ficha, seleccione `System.Runtime.Caching`y, a continuación, haga clic en **Aceptar**.  
  
#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a>Para cambiar el destino es .NET Framework en un proyecto de Visual C#  
  
1.  En **el Explorador de soluciones**, haga clic en el nombre del proyecto y, a continuación, haga clic en **propiedades**.  
  
     Se muestra la ventana Propiedades de la aplicación.  
  
2.  Haga clic en la pestaña **Aplicación** .  
  
3.  En el **.NET framework de destino** lista, seleccione [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]. (No seleccione **.NET Framework 4 Client Profile**.)  
  
4.  Agregue una referencia al ensamblado de almacenamiento en caché siguiendo estos pasos:  
  
    1.  Haga clic en el **referencias** carpeta y, a continuación, haga clic en **Agregar referencia**.  
  
    2.  Seleccione el **.NET** ficha, seleccione `System.Runtime.Caching`y, a continuación, haga clic en **Aceptar**.  
  
## <a name="adding-a-button-to-the-wpf-window"></a>Agregar un botón a la ventana de WPF  
 A continuación, agregará un control de botón y crear un controlador de eventos para el botón `Click` eventos. Después agregará código para por lo que al hacer clic en el botón, el contenido del archivo de texto se almacena en caché y se muestran.  
  
#### <a name="to-add-a-button-control"></a>Para agregar un control de botón  
  
1.  En **el Explorador de soluciones**, haga doble clic en el archivo MainWindow.xaml para abrirlo.  
  
2.  Desde el **cuadro de herramientas**, en **controles WPF comunes**, arrastre un `Button` el control a la `MainWindow` ventana.  
  
3.  En el **propiedades** ventana, establezca el `Content` propiedad de la `Button` el control a **obtener caché**.  
  
## <a name="initializing-the-cache-and-caching-an-entry"></a>Inicializar la memoria caché y almacenamiento en caché una entrada  
 A continuación, agregará el código para llevar a cabo las siguientes tareas:  
  
-   Cree una instancia de la clase de caché, es decir, se creará una instancia de un nuevo <xref:System.Runtime.Caching.MemoryCache> objeto.  
  
-   Especificar que la memoria caché usa un <xref:System.Runtime.Caching.HostFileChangeMonitor> objeto que se va a supervisar los cambios en el archivo de texto.  
  
-   Leer el archivo de texto y su contenido en caché como una entrada de caché.  
  
-   Mostrar el contenido del archivo de texto almacenado en caché.  
  
#### <a name="to-create-the-cache-object"></a>Para crear el objeto de caché  
  
1.  Haga doble clic en el botón que acaba de agregar para crear un controlador de eventos en el archivo MainWindow.xaml.cs o MainWindow.Xaml.vb.  
  
2.  En la parte superior del archivo (antes de la declaración de clase), agregue el siguiente `Imports` (Visual Basic) o `using` instrucciones (C#):  
  
    ```csharp  
    using System.Runtime.Caching;  
    using System.IO;  
    ```  
  
    ```vb  
    Imports System.Runtime.Caching  
    Imports System.IO  
    ```  
  
3.  En el controlador de eventos, agregue el código siguiente para crear instancias del objeto de caché:  
  
    ```csharp  
    ObjectCache cache = MemoryCache.Default;  
    ```  
  
    ```vb  
    Dim cache As ObjectCache = MemoryCache.Default  
    ```  
  
     La <xref:System.Runtime.Caching.ObjectCache> clase es una clase integrada que proporciona una caché de objetos en memoria.  
  
4.  Agregue el código siguiente para leer el contenido de una entrada de caché con nombre `filecontents`:  
  
    ```vb  
    Dim fileContents As String = TryCast(cache("filecontents"), String)  
    ```  
  
    ```csharp  
    string fileContents = cache["filecontents"] as string;  
    ```  
  
5.  Agregue el código siguiente para comprobar si la entrada de caché con nombre `filecontents` existe:  
  
    ```vb  
    If fileContents Is Nothing Then  
  
    End If  
    ```  
  
    ```csharp  
    if (fileContents == null)  
    {  
  
    }  
    ```  
  
     Si la entrada de caché especificado no existe, debe leer el archivo de texto y agréguela como una entrada de caché a la memoria caché.  
  
6.  En el `if/then` bloquear, agregue el código siguiente para crear un nuevo <xref:System.Runtime.Caching.CacheItemPolicy> objeto que especifica que la entrada de caché expire después de 10 segundos.  
  
    ```vb  
    Dim policy As New CacheItemPolicy()  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)  
    ```  
  
    ```csharp  
    CacheItemPolicy policy = new CacheItemPolicy();  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);  
    ```  
  
     Si no se proporciona ninguna información de expulsión o expiración, el valor predeterminado es <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, lo que significa que las entradas de caché no expire nunca basándose únicamente en un tiempo absoluto. En su lugar, las entradas de caché expiran solo cuando hay presión de memoria. Como práctica recomendada, debe proporcionar siempre explícitamente absoluta o una fecha de expiración de fachadas.  
  
7.  Dentro de la `if/then` bloquear y después del código que agregó en el paso anterior, agregue el código siguiente para crear una colección para las rutas de acceso de archivo que desea supervisar y para agregar la ruta de acceso del archivo de texto a la colección:  
  
    ```vb  
    Dim filePaths As New List(Of String)()  
    filePaths.Add("c:\cache\cacheText.txt")  
    ```  
  
    ```csharp  
    List<string> filePaths = new List<string>();  
    filePaths.Add("c:\\cache\\cacheText.txt");  
    ```  
  
    > [!NOTE]
    >  Si el archivo de texto que desea usar no es `c:\cache\cacheText.txt`, especifique la ruta de acceso donde está el archivo de texto que desea utilizar.  
  
8.  Después del código que agregó en el paso anterior, agregue el código siguiente para agregar un nuevo <xref:System.Runtime.Caching.HostFileChangeMonitor> supervisa el objeto a la colección de cambio para la entrada de caché:  
  
    ```vb  
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))  
    ```  
  
    ```csharp  
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));  
    ```  
  
     La <xref:System.Runtime.Caching.HostFileChangeMonitor> objeto supervisa la ruta de acceso del archivo de texto y notifica a la memoria caché si se producen cambios. En este ejemplo, la entrada de caché expirará si cambia el contenido del archivo.  
  
9. A continuación el código que agregó en el paso anterior, agregue el código siguiente para leer el contenido del archivo de texto:  
  
    ```vb  
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()  
    ```  
  
    ```csharp  
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + + "\n" + DateTime.Now;   
    ```  
  
     Se agrega la marca de tiempo de fecha y hora para que puedan ver cuando expire la entrada de caché.  
  
10. Después del código que agregó en el paso anterior, agregue el código siguiente para insertar el contenido del archivo en el objeto de caché como un <xref:System.Runtime.Caching.CacheItem> instancia:  
  
    ```vb  
    cache.Set("filecontents", fileContents, policy)  
    ```  
  
    ```csharp  
    cache.Set("filecontents", fileContents, policy);  
    ```  
  
     Especifique información sobre cómo debe expulsarse la entrada de caché pasando el <xref:System.Runtime.Caching.CacheItemPolicy> objeto que creó anteriormente como un parámetro.  
  
11. Después de la `if/then` bloquear, agregue el código siguiente para mostrar el contenido del archivo almacenado en caché en un cuadro de mensaje:  
  
    ```vb  
    MessageBox.Show(fileContents)  
    ```  
  
    ```csharp  
    MessageBox.Show(fileContents);  
    ```  
  
12. En el **generar** menú, haga clic en **WPFCaching generar** para compilar el proyecto.  
  
## <a name="testing-caching-in-the-wpf-application"></a>Pruebas de almacenamiento en caché en la aplicación de WPF  
 Ahora puede probar la aplicación.  
  
#### <a name="to-test-caching-in-the-wpf-application"></a>Para probar el almacenamiento en caché en la aplicación de WPF  
  
1.  Presione CTRL+F5 para ejecutar la aplicación.  
  
     El `MainWindow` se muestra la ventana.  
  
2.  Haga clic en **obtener caché**.  
  
     El contenido almacenado en caché del archivo de texto se muestra en un cuadro de mensaje. Tenga en cuenta la marca de tiempo en el archivo.  
  
3.  Cierre el cuadro de mensaje y, a continuación, haga clic en **obtener caché** nuevo**.**  
  
     Se ha modificado la marca de tiempo. Esto indica que se muestra el contenido almacenado en caché.  
  
4.  Espere 10 segundos o más y, a continuación, haga clic en **obtener caché** nuevo.  
  
     Este tiempo se muestra una nueva marca de tiempo. Esto indica que la directiva deje que la entrada de caché expire y que se muestra el nuevo contenido almacenado en caché.  
  
5.  En un editor de texto, abra el archivo de texto que ha creado. No realice los cambios todavía.  
  
6.  Cierre el cuadro de mensaje y, a continuación, haga clic en **obtener caché** nuevo**.**  
  
     Observe la marca de tiempo de nuevo.  
  
7.  Realiza un cambio en el archivo de texto y, a continuación, guarde el archivo.  
  
8.  Cierre el cuadro de mensaje y, a continuación, haga clic en **obtener caché** nuevo.  
  
     Este cuadro de mensaje contiene el contenido actualizado desde el archivo de texto y una nueva marca de tiempo. Esto indica que el monitor de cambio de archivos de host expulsa la entrada de caché inmediatamente cuando cambia el archivo, incluso si no había expirado el período de tiempo de espera absoluta.  
  
    > [!NOTE]
    >  Puede aumentar el tiempo de expulsión a 20 segundos o más para que tenga más tiempo realizar un cambio en el archivo.  
  
## <a name="code-example"></a>Ejemplo de código  
 Después de completar este tutorial, el código del proyecto que creó parecerán al ejemplo siguiente.  
  
 [!code-csharp[CachingWPFApplications#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.Caching.MemoryCache>  
 <xref:System.Runtime.Caching.ObjectCache>  
 <xref:System.Runtime.Caching>  
 [Almacenamiento en caché en aplicaciones .NET Framework](../../../../docs/framework/performance/caching-in-net-framework-applications.md)
