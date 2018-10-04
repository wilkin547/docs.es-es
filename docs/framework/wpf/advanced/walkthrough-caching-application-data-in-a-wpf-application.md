---
title: 'Tutorial: Almacenar en caché datos de la aplicación en una aplicación de WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: 1eddf3ad52bab6ef4665d7c3691353fa9c54574c
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2018
ms.locfileid: "48264007"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a>Tutorial: Almacenar en caché datos de la aplicación en una aplicación de WPF
El almacenamiento en caché permite almacenar datos en memoria para un acceso rápido. Cuando se tiene acceso a los datos de nuevo, las aplicaciones pueden obtener los datos de la memoria caché en su lugar la recuperación de la fuente original. Esto puede mejorar el rendimiento y la escalabilidad. Además, el almacenamiento en caché permite que los datos estén disponibles cuando el origen de datos no está disponible temporalmente.

 El [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporciona clases que le permiten usar el almacenamiento en caché en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] aplicaciones. Estas clases se encuentran en el <xref:System.Runtime.Caching> espacio de nombres.

> [!NOTE]
>  El <xref:System.Runtime.Caching> espacio de nombres es nuevo en el [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]. Hace que este espacio de nombres de almacenamiento en caché está disponible para todos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] aplicaciones. En versiones anteriores de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], el almacenamiento en caché solo estaba disponible en el espacio de nombres <xref:System.Web> y, por tanto, exigía una dependencia en las clases de ASP.NET.

 En este tutorial se muestra cómo usar la funcionalidad de almacenamiento en caché está disponible en el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] como parte de un [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicación. En el tutorial, almacenar en caché el contenido de un archivo de texto.

 Las tareas que se ilustran en este tutorial son las siguientes:

-   Crear un proyecto de aplicación de WPF.

-   Agregar una referencia a la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].

-   Inicializando una memoria caché.

-   Agregar una entrada de caché que contiene el contenido de un archivo de texto.

-   Proporcionar una directiva de expulsión para la entrada de caché.

-   Supervisión de la ruta de acceso del archivo almacenado en caché y notificar a la instancia de caché acerca de los cambios en los elementos supervisados.

## <a name="prerequisites"></a>Requisitos previos
 Para poder completar este tutorial, necesitará:

-   Microsoft Visual Studio 2010.

-   Un archivo de texto que contiene una pequeña cantidad de texto. (Se mostrará el contenido del archivo de texto en un cuadro de mensaje). El código que se muestra en el tutorial se da por supuesto que está trabajando con el siguiente archivo:

     `c:\cache\cacheText.txt`

     Sin embargo, puede usar cualquier archivo de texto y realizar pequeños cambios en el código en este tutorial.

## <a name="creating-a-wpf-application-project"></a>Crear un proyecto de aplicación de WPF
 Se iniciará mediante la creación de un proyecto de aplicación de WPF.

#### <a name="to-create-a-wpf-application"></a>Para crear una aplicación WPF

1.  Inicie Visual Studio.

2.  En el **archivo** menú, haga clic en **New**y, a continuación, haga clic en **nuevo proyecto**.

     Aparecerá el cuadro de diálogo **Nuevo proyecto**.

3.  En **plantillas instaladas**, seleccione el lenguaje de programación que desea utilizar (**Visual Basic** o **Visual C#**).

4.  En el **nuevo proyecto** cuadro de diálogo, seleccione **aplicación WPF**.

    > [!NOTE]
    >  Si no ve el **aplicación WPF** plantilla, asegúrese de que se usa como destino una versión de la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que es compatible con WPF. En el **nuevo proyecto** cuadro de diálogo, seleccione [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] en la lista.

5.  En el **nombre** texto, escriba un nombre para el proyecto. Por ejemplo, puede escribir **WPFCaching**.

6.  Seleccione el **crear directorio para la solución** casilla de verificación.

7.  Haga clic en **Aceptar**.

     Se abre el Diseñador de WPF en **diseño** ver y muestra el archivo MainWindow.xaml. Visual Studio crea el **mi proyecto** carpeta, el archivo Application.xaml y el archivo MainWindow.xaml.

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a>Destinadas a .NET Framework y agregar una referencia a los ensamblados de almacenamiento en caché
 De forma predeterminada, el destino de las aplicaciones de WPF la [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]. Para usar el <xref:System.Runtime.Caching> espacio de nombres en una aplicación WPF, la aplicación debe tener como destino el [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (no el [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) y debe incluir una referencia al espacio de nombres.

 Por lo tanto, el siguiente paso es cambiar el destino de .NET Framework y agregar una referencia a la <xref:System.Runtime.Caching> espacio de nombres.

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

     Aparecerá el cuadro de diálogo **Cambio de plataforma de destino**.

6.  En el **cambio de plataforma de destino** cuadro de diálogo, haga clic en **Sí**.

     El proyecto se cierra y, a continuación, se vuelve a abrir.

7.  Agregue una referencia al ensamblado de almacenamiento en caché siguiendo estos pasos:

    1.  En **el Explorador de soluciones**, haga clic en el nombre del proyecto y, a continuación, haga clic en **Agregar referencia**.

    2.  Seleccione el **.NET** ficha, seleccione `System.Runtime.Caching`y, a continuación, haga clic en **Aceptar**.

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a>Para cambiar el destino de .NET Framework en un proyecto de Visual C#

1.  En **el Explorador de soluciones**, haga clic en el nombre del proyecto y, a continuación, haga clic en **propiedades**.

     Se muestra la ventana Propiedades de la aplicación.

2.  Haga clic en la pestaña **Aplicación** .

3.  En el **.NET framework de destino** lista, seleccione [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]. (No seleccione **.NET Framework 4 Client Profile**.)

4.  Agregue una referencia al ensamblado de almacenamiento en caché siguiendo estos pasos:

    1.  Haga clic en el **referencias** carpeta y, a continuación, haga clic en **Agregar referencia**.

    2.  Seleccione el **.NET** ficha, seleccione `System.Runtime.Caching`y, a continuación, haga clic en **Aceptar**.

## <a name="adding-a-button-to-the-wpf-window"></a>Agregar un botón a la ventana de WPF
 A continuación, agregará un control de botón y crear un controlador de eventos del botón `Click` eventos. Más adelante agregará código para por lo que al hacer clic en el botón, el contenido del archivo de texto se almacena en caché y se muestran.

#### <a name="to-add-a-button-control"></a>Para agregar un control de botón

1.  En **el Explorador de soluciones**, haga doble clic en el archivo MainWindow.xaml para abrirlo.

2.  Desde el **cuadro de herramientas**, en **controles WPF comunes**, arrastre un `Button` el control a la `MainWindow` ventana.

3.  En el **propiedades** ventana, establezca el `Content` propiedad de la `Button` el control a **obtener caché**.

## <a name="initializing-the-cache-and-caching-an-entry"></a>Inicializar la memoria caché y almacenamiento en caché una entrada
 A continuación, agregará el código para llevar a cabo las siguientes tareas:

-   Cree una instancia de la clase de caché, es decir, se creará una instancia de un nuevo <xref:System.Runtime.Caching.MemoryCache> objeto.

-   Especificar que la memoria caché usa un <xref:System.Runtime.Caching.HostFileChangeMonitor> objetos para supervisar los cambios en el archivo de texto.

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

3.  En el controlador de eventos, agregue el código siguiente para crear una instancia del objeto de caché:

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     El <xref:System.Runtime.Caching.ObjectCache> es una clase integrada que proporciona una caché de objetos en memoria.

4.  Agregue el código siguiente para leer el contenido de una entrada de caché denominada `filecontents`:

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5.  Agregue el código siguiente para comprobar si la entrada de caché denominada `filecontents` existe:

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     Si la entrada de caché especificado no existe, debe leer el archivo de texto y agregarlo como una entrada de caché a la memoria caché.

6.  En el `if/then` en bloques, agregue el código siguiente para crear un nuevo <xref:System.Runtime.Caching.CacheItemPolicy> objeto que especifica que la entrada de caché expira transcurridos 10 segundos.

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     Si se proporciona ninguna información de expulsión o expiración, el valor predeterminado es <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, lo que significa que las entradas de caché no expiren nunca basándose solo en un tiempo absoluto. En su lugar, las entradas de caché expiran solo cuando hay presión de memoria. Como práctica recomendada, debe proporcionar siempre explícitamente absoluta o una fecha de expiración de fachadas.

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
    >  Si el archivo de texto que desea usar no es `c:\cache\cacheText.txt`, especifique la ruta de acceso donde está el archivo de texto que desea usar.

8.  Siguiendo el código que agregó en el paso anterior, agregue el código siguiente para agregar un nuevo <xref:System.Runtime.Caching.HostFileChangeMonitor> supervisa el objeto a la colección de cambios para la entrada de caché:

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     La <xref:System.Runtime.Caching.HostFileChangeMonitor> objeto supervisa la ruta de acceso del archivo de texto y notifica a la memoria caché si se producen cambios. En este ejemplo, la entrada de caché expirará si cambia el contenido del archivo.

9. Después del código que agregó en el paso anterior, agregue el código siguiente para leer el contenido del archivo de texto:

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + + "\n" + DateTime.Now;
    ```

     Se agrega la marca de tiempo de fecha y hora para que puedan ver cuando expira la entrada de caché.

10. Siguiendo el código que agregó en el paso anterior, agregue el siguiente código para insertar el contenido del archivo en el objeto de caché como un <xref:System.Runtime.Caching.CacheItem> instancia:

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     Especifique información acerca de cómo debe expulsarse la entrada de caché pasando el <xref:System.Runtime.Caching.CacheItemPolicy> objeto que creó anteriormente como un parámetro.

11. Después de la `if/then` en bloques, agregue el código siguiente para mostrar el contenido del archivo almacenado en caché en un cuadro de mensaje:

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. En el **compilar** menú, haga clic en **WPFCaching compilación** para compilar el proyecto.

## <a name="testing-caching-in-the-wpf-application"></a>Pruebas de almacenamiento en caché en la aplicación de WPF
 Ahora puede probar la aplicación.

#### <a name="to-test-caching-in-the-wpf-application"></a>Para probar el almacenamiento en caché en la aplicación de WPF

1.  Presione CTRL+F5 para ejecutar la aplicación.

     El `MainWindow` se muestra la ventana.

2.  Haga clic en **obtener memoria caché**.

     Se muestra el contenido almacenado en caché del archivo de texto en un cuadro de mensaje. Tenga en cuenta la marca de tiempo en el archivo.

3.  Cierre el cuadro de mensaje y, a continuación, haga clic en **obtener caché** nuevo **.**

     Se ha modificado la marca de tiempo. Esto indica que se muestra el contenido almacenado en caché.

4.  Espere 10 segundos o más y, a continuación, haga clic en **obtener caché** nuevo.

     Este tiempo se muestra una marca de tiempo nueva. Esto indica que la directiva que permite la entrada de caché expiran y que se muestra el nuevo contenido en caché.

5.  En un editor de texto, abra el archivo de texto que ha creado. No realice los cambios todavía.

6.  Cierre el cuadro de mensaje y, a continuación, haga clic en **obtener caché** nuevo **.**

     Observe nuevamente la marca de tiempo.

7.  Realice un cambio en el archivo de texto y, a continuación, guarde el archivo.

8.  Cierre el cuadro de mensaje y, a continuación, haga clic en **obtener caché** nuevo.

     Este cuadro de mensaje contiene el contenido actualizado desde el archivo de texto y una marca de tiempo nueva. Esto indica que la supervisión de cambios de archivos host expulsa la entrada de caché inmediatamente cuando cambia el archivo, incluso si no ha expirado el período de tiempo de espera absoluta.

    > [!NOTE]
    >  Puede aumentar el tiempo de expulsión en 20 segundos o más para dar más tiempo para que pueda realizar un cambio en el archivo.

## <a name="code-example"></a>Ejemplo de código
 Después de completar este tutorial, el código para el proyecto creó tendrá un aspecto similar en el ejemplo siguiente.

 [!code-csharp[CachingWPFApplications#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [Almacenamiento en caché en aplicaciones .NET Framework](../../../../docs/framework/performance/caching-in-net-framework-applications.md)