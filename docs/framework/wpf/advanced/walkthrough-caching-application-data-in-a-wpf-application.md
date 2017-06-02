---
title: "Tutorial: Almacenar en cach&#233; datos de la aplicaci&#243;n en una aplicaci&#243;n de WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "almacenar en caché [.NET Framework]"
  - "almacenamiento en caché [WPF]"
  - "tutoriales [WPF], almacenar en caché"
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Tutorial: Almacenar en cach&#233; datos de la aplicaci&#243;n en una aplicaci&#243;n de WPF
El almacenamiento en caché permite almacenar los datos en memoria para poder acceder a ellos rápidamente.  Cuando se tiene acceso de nuevo a los datos, las aplicaciones pueden obtener los datos de la memoria caché en lugar de recuperarlos del origen inicial.  Esto puede mejorar el rendimiento y la escalabilidad.  Además, con el almacenamiento en caché, los datos siguen estando disponibles si el origen de datos temporalmente no lo está.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporciona clases que permiten usar el almacenamiento en caché de aplicaciones de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] .  Estas clases se encuentran en el espacio de nombres <xref:System.Runtime.Caching> .  
  
> [!NOTE]
>  El espacio de nombres <xref:System.Runtime.Caching> es nuevo en [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  Con este espacio de nombres, el almacenamiento en caché está disponible en todas las aplicaciones de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  En versiones anteriores de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], el almacenamiento en caché solo estaba disponible en el espacio de nombres <xref:System.Web> y, por tanto, necesitaba una dependencia en las clases de ASP.NET.  
  
 En este tutorial se muestra cómo se usa la funcionalidad de almacenamiento en caché que está disponible en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] como parte de una aplicación [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  En el tutorial, va a almacenar el contenido de un archivo de texto en la memoria caché.  
  
 Las tareas que se ilustran en este tutorial son las siguientes:  
  
-   Crear un proyecto de aplicación WPF.  
  
-   Agregar una referencia a [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
-   Inicializar una memoria caché.  
  
-   Agregar una entrada de caché que tenga el contenido de un archivo de texto.  
  
-   Proporcionar una directiva de expulsión para la entrada en caché.  
  
-   Supervisar la ruta de acceso del archivo en caché y notificar a la instancia de caché los cambios que se producen en el elemento supervisado.  
  
## Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Microsoft [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   Un archivo de texto que contenga una pequeña cantidad de texto.  \(Mostrará el contenido del archivo de texto en un cuadro de mensaje\). En el código que se muestra en el tutorial se supone que está trabajando con el archivo siguiente:  
  
     `c:\cache\cacheText.txt`  
  
     Sin embargo, puede utilizar cualquier archivo de texto y realizar pequeños cambios en el código de este tutorial.  
  
## Crear un proyecto de aplicación WPF  
 Para empezar, creará un proyecto de aplicación WPF.  
  
#### Para crear una aplicación WPF  
  
1.  Inicie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
2.  En el menú **Archivo**, haga clic en **Nuevo** y, a continuación, en **Nuevo proyecto**.  
  
     Aparecerá el cuadro de diálogo **Nuevo proyecto**.  
  
3.  En **Plantillas instaladas**, seleccione el lenguaje de programación que desee utilizar \(**Visual Basic** o **Visual C\#**\).  
  
4.  En el cuadro de diálogo **Nuevo proyecto**, seleccione **Aplicación WPF**.  
  
    > [!NOTE]
    >  Si la plantilla **Aplicación WPF** no está visible, asegúrese de utilizar una versión de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que admita WPF.  En el cuadro de diálogo **Nuevo proyecto**, seleccione [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] en la lista.  
  
5.  En el cuadro de texto **Nombre**, escriba un nombre para el proyecto.  Por ejemplo, puede especificar WPFCaching.  
  
6.  Active la casilla **Crear directorio para la solución**.  
  
7.  Haga clic en **Aceptar**.  
  
     WPF Designer se abrirá en la **Vista de diseño** con el archivo MainWindow.xaml.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] crea la carpeta **My Project**, el archivo Application.xaml y el archivo MainWindow.xaml.  
  
## Usar .NET Framework como destino y agregar una referencia a los ensamblados de almacenamiento en caché  
 De forma predeterminada, el destino de las aplicaciones WPF es [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].  Para utilizar el espacio de nombres <xref:System.Runtime.Caching> en una aplicación WPF, la aplicación debe tener como destino [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] \(no [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]\), y debe incluir una referencia al espacio de nombres.  
  
 Por consiguiente, el paso siguiente es cambiar la versión de .NET Framework de destino y agregar una referencia al espacio de nombres <xref:System.Runtime.Caching>.  
  
> [!NOTE]
>  El procedimiento para cambiar la versión de .NET Framework de destino es diferente en un proyecto de Visual Basic y en un proyecto de Visual C\#.  
  
#### Para cambiar la versión de .NET Framework de destino en Visual Basic  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Propiedades**.  
  
     Se mostrará la ventana Propiedades de la aplicación.  
  
2.  Haga clic en la ficha **Compilar**.  
  
3.  En la parte inferior de la ventana, haga clic en **Opciones de compilación avanzadas…**.  
  
     Se muestra el cuadro de diálogo **Configuración de compilador avanzada**.  
  
4.  En la lista de **Marco de destino \(todas las configuraciones\)** , seleccione [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  No seleccione [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].\)  
  
5.  Haga clic en **Aceptar**.  
  
     Aparecerá el cuadro de diálogo **Cambio de versión de .NET Framework de destino**.  
  
6.  En el cuadro de diálogo **Cambio de versión de .NET Framework de destino**, haga clic en **Sí**.  
  
     El proyecto se cierra y se vuelve a abrir.  
  
7.  Agregue una referencia al ensamblado de almacenamiento en caché siguiendo estos pasos:  
  
    1.  En el **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Agregar referencia**.  
  
    2.  Seleccione la pestaña **.NET**, seleccione `System.Runtime.Caching` y, a continuación, haga clic en **Aceptar**.  
  
#### Para cambiar la versión de .NET Framework de destino de un proyecto de Visual C\#  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Propiedades**.  
  
     Se mostrará la ventana Propiedades de la aplicación.  
  
2.  Haga clic en la ficha **Aplicación**.  
  
3.  En la lista **Versión de .NET Framework de destino**, seleccione [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  \(No seleccione **.NET Framework 4 Client Profile**\).  
  
4.  Agregue una referencia al ensamblado de almacenamiento en caché siguiendo estos pasos:  
  
    1.  Haga clic con el botón secundario del mouse en la carpeta **Referencias** y, a continuación, haga clic en **Agregar referencia**.  
  
    2.  Seleccione la pestaña **.NET**, seleccione `System.Runtime.Caching` y, a continuación, haga clic en **Aceptar**.  
  
## Agregar un botón a la ventana de WPF  
 A continuación, agregará un control de botón y creará un controlador de eventos para el evento `Click` del botón.  Agregará más adelante código de modo que, cuando se haga clic en el botón, el contenido del archivo de texto se almacene en caché y se muestre.  
  
#### Para agregar un control de botón  
  
1.  En el **Explorador de soluciones**, haga doble clic en el archivo MainWindow.xaml para abrirlo.  
  
2.  Desde el **Cuadro de herramientas**, en **Controles WPF comunes**, arrastre un control `Button` a la ventana `MainWindow`.  
  
3.  En la ventana **Propiedades**, establezca la propiedad `Content` del control `Button` en Get Cache.  
  
## Inicializar la memoria caché y almacenar una entrada en caché  
 A continuación, agregará el código correspondiente para realizar las siguientes tareas:  
  
-   Crear una instancia de la clase Cache; es decir, crear una instancia de un nuevo objeto <xref:System.Runtime.Caching.MemoryCache>.  
  
-   Especificar que la memoria caché use un objeto <xref:System.Runtime.Caching.HostFileChangeMonitor> para supervisar los cambios del archivo de texto.  
  
-   Leer el archivo de texto y almacenar en caché su contenido como entrada.  
  
-   Mostrar el contenido del archivo de texto almacenado en caché.  
  
#### Para crear el objeto de caché  
  
1.  Haga doble clic en el botón que acaba de agregar para crear un controlador de eventos en el archivo MainWindow.xaml.cs o MainWindow.Xaml.vb.  
  
2.  En la parte superior del archivo \(antes de la declaración de clase\), agregue las siguientes instrucciones `Imports` \(Visual Basic\) o `using` \(C\#\):  
  
    ```csharp  
    using System.Runtime.Caching;  
    using System.IO;  
    ```  
  
    ```vb  
    Imports System.Runtime.Caching  
    Imports System.IO  
    ```  
  
3.  En el controlador de eventos, agregue el código siguiente para crear una instancia del objeto de caché:  
  
    ```csharp  
    ObjectCache cache = MemoryCache.Default;  
    ```  
  
    ```vb  
    Dim cache As ObjectCache = MemoryCache.Default  
    ```  
  
     La clase <xref:System.Runtime.Caching.ObjectCache> es una clase integrada que proporciona una memoria caché de objetos en memoria.  
  
4.  Agregue el siguiente código para leer el contenido de una entrada de caché denominada `filecontents`:  
  
    ```vb  
    Dim fileContents As String = TryCast(cache("filecontents"), String)  
    ```  
  
    ```csharp  
    string fileContents = cache["filecontents"] as string;  
    ```  
  
5.  Agregue el siguiente código para comprobar si la entrada de caché denominada `filecontents` existe:  
  
    ```vb  
    If fileContents Is Nothing Then  
  
    End If  
    ```  
  
    ```csharp  
    if (fileContents == null)  
    {  
  
    }  
    ```  
  
     Si la entrada de la memoria caché especificada no existe, debe leer el archivo de texto y agregarlo a la memoria caché como entrada.  
  
6.  En el bloque `if/then`, agregue el siguiente código para crear un nuevo objeto <xref:System.Runtime.Caching.CacheItemPolicy> que especifique que la entrada de caché expire después de 10 segundos.  
  
    ```vb  
    Dim policy As New CacheItemPolicy()  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)  
    ```  
  
    ```csharp  
    CacheItemPolicy policy = new CacheItemPolicy();  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);  
    ```  
  
     Si no se proporciona información de expulsión o expiración, el valor predeterminado es <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, lo que significa que las entradas de caché no expiran nunca solo en función de un valor de tiempo absoluto.  Por el contrario, las entradas de caché únicamente expirarán cuando haya presión de memoria.  Como procedimiento recomendado, debería proporcionar siempre explícitamente un valor absoluto o una fecha de expiración variable.  
  
7.  En el bloque `if/then`, detrás el código que agregó en el paso anterior, agregue el siguiente código con el fin de crear una colección para las rutas de acceso del archivo que desea supervisar y para agregar la ruta de acceso del archivo de texto a la colección:  
  
    ```vb  
    Dim filePaths As New List(Of String)()  
    filePaths.Add("c:\cache\cacheText.txt")  
    ```  
  
    ```csharp  
    List<string> filePaths = new List<string>();  
    filePaths.Add("c:\\cache\\cacheText.txt");  
    ```  
  
    > [!NOTE]
    >  Si el archivo de texto que desea utilizar no es `c:\cache\cacheText.txt`, especifique la ruta de acceso donde se encuentra el archivo de texto que desea utilizar.  
  
8.  Detrás del código que agregó en el paso anterior, agregue el siguiente código para incorporar un nuevo objeto <xref:System.Runtime.Caching.HostFileChangeMonitor> a la colección de supervisores de cambios de la entrada de caché:  
  
    ```vb  
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))  
    ```  
  
    ```csharp  
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));  
    ```  
  
     El objeto <xref:System.Runtime.Caching.HostFileChangeMonitor> supervisa la ruta de acceso del archivo de texto y notifica a la memoria caché si se produce algún cambio.  En este ejemplo, la entrada de caché expirará si el contenido del archivo cambia.  
  
9. Detrás del código que agregó en el paso anterior, agregue el código siguiente al método para leer el contenido del archivo de texto:  
  
    ```vb  
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()  
    ```  
  
    ```csharp  
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + + "\n" + DateTime.Now;   
    ```  
  
     Se agrega la marca de tiempo de fecha y hora de modo que pueda ver cuándo expira la entrada de caché.  
  
10. Detrás del código que agregó en el paso anterior agregue el código siguiente para insertar el contenido del archivo en el objeto de caché como una instancia de <xref:System.Runtime.Caching.CacheItem>:  
  
    ```vb  
    cache.Set("filecontents", fileContents, policy)  
    ```  
  
    ```csharp  
    cache.Set("filecontents", fileContents, policy);  
    ```  
  
     Puede especificar información sobre cómo debe expulsarse la entrada de caché pasando el objeto <xref:System.Runtime.Caching.CacheItemPolicy> que creó previamente como parámetro del método.  
  
11. Detrás del bloque `if/then`, agregue el siguiente código para mostrar el contenido del archivo almacenado en caché en un cuadro de mensaje:  
  
    ```vb  
    MessageBox.Show(fileContents)  
    ```  
  
    ```csharp  
    MessageBox.Show(fileContents);  
    ```  
  
12. En el menú **Generar**, haga clic en **Generar WPFCaching** para compilar el proyecto.  
  
## Probar el almacenamiento en caché en la aplicación WPF  
 Ya puede probar la aplicación.  
  
#### Para probar el almacenamiento en caché en la aplicación WPF  
  
1.  Presione CTRL\+F5 para ejecutar la aplicación.  
  
     Se muestra la ventana `MainWindow`.  
  
2.  Haga clic en **Get Cache**.  
  
     El contenido almacenado en caché del archivo de texto se muestra en un cuadro de mensaje.  Observe la marca de tiempo del archivo.  
  
3.  Cierre el cuadro de mensaje y, a continuación, haga clic en **Get Cache**   **de nuevo.**  
  
     La marca de tiempo no ha cambiado.  Esto indica que se va a mostrar el contenido almacenado en caché.  
  
4.  Espere 10 segundos o más y, a continuación, haga clic de nuevo en **Get Cache**.  
  
     Ahora aparece una nueva marca de tiempo.  Esto indica que la directiva ha permitido que la entrada de caché expire y que se muestra el nuevo contenido almacenado.  
  
5.  En un editor de texto, abra el archivo de texto que creó.  No realice ninguna modificación todavía.  
  
6.  Cierre el cuadro de mensaje y, a continuación, haga clic en **Get Cache**   **de nuevo.**  
  
     Observe la marca de tiempo de nuevo.  
  
7.  Realice un cambio en el archivo de texto y, a continuación, guarde el archivo.  
  
8.  Cierre el cuadro de mensaje y, a continuación, haga clic en **Get Cache** una vez más.  
  
     Este cuadro de mensaje incluye el contenido actualizado del archivo de texto y una nueva marca de tiempo.  Esto indica que el supervisor de cambios del archivo host expulsó la entrada de caché inmediatamente cuando cambió el archivo, aunque el período de tiempo de espera absoluto no había expirado.  
  
    > [!NOTE]
    >  Puede aumentar el tiempo de expulsión a 20 segundos o más si desea disponer de más tiempo para modificar el archivo.  
  
## Ejemplo de código  
 Después de completar este tutorial, el código del proyecto que creó tendrá un aspecto similar al del ejemplo siguiente.  
  
 [!code-csharp[CachingWPFApplications#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]  
  
## Vea también  
 <xref:System.Runtime.Caching.MemoryCache>   
 <xref:System.Runtime.Caching.ObjectCache>   
 <xref:System.Runtime.Caching>   
 [Almacenamiento en caché en aplicaciones .NET Framework](../../../../docs/framework/performance/caching-in-net-framework-applications.md)