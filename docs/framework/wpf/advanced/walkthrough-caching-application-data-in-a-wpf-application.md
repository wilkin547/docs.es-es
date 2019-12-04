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
ms.openlocfilehash: 922d91466731b331cc409cc362c4ada2c287916a
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715887"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a>Tutorial: Almacenar en caché datos de la aplicación en una aplicación de WPF
El almacenamiento en caché permite almacenar datos en memoria para un acceso rápido. Cuando se vuelve a acceder a los datos, las aplicaciones pueden obtenerlos de la memoria caché en lugar de recuperarlos de la fuente original. Esto puede mejorar el rendimiento y la escalabilidad. Además, el almacenamiento en caché permite que los datos estén disponibles cuando el origen de datos no está disponible temporalmente.

 El .NET Framework proporciona clases que permiten usar el almacenamiento en caché en aplicaciones de .NET Framework. Estas clases se encuentran en el espacio de nombres <xref:System.Runtime.Caching>.

> [!NOTE]
> El espacio de nombres <xref:System.Runtime.Caching> es nuevo en el .NET Framework 4. Este espacio de nombres hace que el almacenamiento en caché esté disponible para todas .NET Framework aplicaciones. En versiones anteriores del .NET Framework, el almacenamiento en caché solo estaba disponible en el espacio de nombres <xref:System.Web> y, por tanto, requería una dependencia en las clases ASP.NET.

 En este tutorial se muestra cómo usar la funcionalidad de almacenamiento en caché que está disponible en el .NET Framework como parte de una aplicación [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. En el tutorial, almacenará en caché el contenido de un archivo de texto.

 Las tareas que se ilustran en este tutorial son las siguientes:

- Crear un proyecto de aplicación de WPF.

- Agregar una referencia al .NET Framework 4.

- Inicializar una memoria caché.

- Agregar una entrada de caché que incluye el contenido de un archivo de texto.

- Proporcionar una directiva de expulsión para la entrada de caché.

- Supervisar la ruta de acceso del archivo en caché y notificar a la instancia de caché los cambios en el elemento supervisado.

## <a name="prerequisites"></a>Requisitos previos
 Para poder completar este tutorial, necesitará:

- Visual Studio 2010.

- Un archivo de texto que contiene una pequeña cantidad de texto. (Se mostrará el contenido del archivo de texto en un cuadro de mensaje). En el código que se muestra en el tutorial se da por supuesto que está trabajando con el siguiente archivo:

     `c:\cache\cacheText.txt`

     Sin embargo, puede usar cualquier archivo de texto y realizar pequeños cambios en el código de este tutorial.

## <a name="creating-a-wpf-application-project"></a>Crear un proyecto de aplicación de WPF
 Comenzará creando un proyecto de aplicación de WPF.

#### <a name="to-create-a-wpf-application"></a>Para crear una aplicación WPF

1. Inicie Visual Studio.

2. En el menú **archivo** , haga clic en **nuevo**y, a continuación, haga clic en **nuevo proyecto**.

     Aparecerá el cuadro de diálogo **Nuevo proyecto**.

3. En **plantillas instaladas**, seleccione el lenguaje de programación que desea usar (**Visual Basic** o **Visual C#** ).

4. En el cuadro de diálogo **nuevo proyecto** , seleccione **aplicación WPF**.

    > [!NOTE]
    > Si no ve la plantilla de **aplicación de WPF** , asegúrese de que tiene como destino una versión de la .NET Framework que admite WPF. En el cuadro de diálogo **nuevo proyecto** , seleccione .NET Framework 4 en la lista.

5. En el cuadro de texto **nombre** , escriba un nombre para el proyecto. Por ejemplo, puede escribir **WPFCaching**.

6. Active la casilla **Crear directorio para la solución**.

7. Haga clic en **Aceptar**.

     WPF Designer se abre en la vista de **diseño** y muestra el archivo MainWindow. Xaml. Visual Studio crea la carpeta **mi proyecto** , el archivo Application. XAML y el archivo MainWindow. Xaml.

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a>Establecer como destino el .NET Framework y agregar una referencia a los ensamblados de almacenamiento en caché
 De forma predeterminada, las aplicaciones de WPF tienen como destino el perfil de cliente de .NET Framework 4. Para usar el espacio de nombres <xref:System.Runtime.Caching> en una aplicación de WPF, la aplicación debe tener como destino el .NET Framework 4 (no el perfil de cliente de .NET Framework 4) y debe incluir una referencia al espacio de nombres.

 Por lo tanto, el siguiente paso es cambiar el destino de .NET Framework y agregar una referencia al espacio de nombres <xref:System.Runtime.Caching>.

> [!NOTE]
> El procedimiento para cambiar el destino de .NET Framework es diferente en un proyecto de Visual Basic y en C# un proyecto visual.

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a>Para cambiar la .NET Framework de destino en Visual Basic

1. En el **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **propiedades**.

     Se muestra la ventana Propiedades de la aplicación.

2. Haga clic en la pestaña **Compilar**.

3. En la parte inferior de la ventana, haga clic en **Opciones de compilación avanzadas.** .

     Se muestra el cuadro de diálogo **configuración de compilador avanzada** .

4. En la lista versión de **.NET Framework de destino (todas las configuraciones)** , seleccione .NET Framework 4. (No seleccione .NET Framework 4 Client Profile).

5. Haga clic en **Aceptar**.

     Aparecerá el cuadro de diálogo **Cambio de plataforma de destino**.

6. En el cuadro de diálogo cambio de versión de **.NET Framework de destino** , haga clic en **sí**.

     El proyecto está cerrado y se vuelve a abrir.

7. Agregue una referencia al ensamblado de almacenamiento en caché siguiendo estos pasos:

    1. En **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Agregar referencia**.

    2. Seleccione la pestaña **.net** , seleccione `System.Runtime.Caching`y, a continuación, haga clic en **Aceptar**.

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a>Para cambiar el .NET Framework de destino en un C# proyecto visual

1. En **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **propiedades**.

     Se muestra la ventana Propiedades de la aplicación.

2. Haga clic en la pestaña **Aplicación** .

3. En la lista **plataforma de destino** , seleccione .NET Framework 4. (No seleccione **.NET Framework 4 Client Profile**).

4. Agregue una referencia al ensamblado de almacenamiento en caché siguiendo estos pasos:

    1. Haga clic con el botón secundario en la carpeta **referencias** y después haga clic en **Agregar referencia**.

    2. Seleccione la pestaña **.net** , seleccione `System.Runtime.Caching`y, a continuación, haga clic en **Aceptar**.

## <a name="adding-a-button-to-the-wpf-window"></a>Agregar un botón a la ventana de WPF
 A continuación, agregará un control de botón y creará un controlador de eventos para el evento de `Click` del botón. Más adelante agregará código al hacer clic en el botón, el contenido del archivo de texto se almacenará en la memoria caché y se mostrará.

#### <a name="to-add-a-button-control"></a>Para agregar un control de botón

1. En **Explorador de soluciones**, haga doble clic en el archivo MainWindow. XAML para abrirlo.

2. En el **cuadro de herramientas**, en **controles WPF comunes**, arrastre un control `Button` a la ventana `MainWindow`.

3. En la ventana **propiedades** , establezca la propiedad `Content` del control `Button` en **obtener caché**.

## <a name="initializing-the-cache-and-caching-an-entry"></a>Inicialización de la memoria caché y almacenamiento en caché de una entrada
 A continuación, agregará el código para realizar las siguientes tareas:

- Cree una instancia de la clase cache, es decir, creará una instancia de un nuevo objeto <xref:System.Runtime.Caching.MemoryCache>.

- Especifica que la memoria caché utiliza un objeto <xref:System.Runtime.Caching.HostFileChangeMonitor> para supervisar los cambios en el archivo de texto.

- Lea el archivo de texto y almacene en caché su contenido como una entrada de caché.

- Mostrar el contenido del archivo de texto almacenado en caché.

#### <a name="to-create-the-cache-object"></a>Para crear el objeto de caché

1. Haga doble clic en el botón que acaba de agregar para crear un controlador de eventos en el archivo MainWindow.xaml.cs o MainWindow. Xaml. VB.

2. En la parte superior del archivo (antes de la declaración de clase), agregue las siguientes instrucciones `Imports` (Visual Basic)C#o `using` ():

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3. En el controlador de eventos, agregue el código siguiente para crear una instancia del objeto de caché:

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     La clase <xref:System.Runtime.Caching.ObjectCache> es una clase integrada que proporciona una memoria caché de objetos en memoria.

4. Agregue el código siguiente para leer el contenido de una entrada de caché denominada `filecontents`:

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5. Agregue el código siguiente para comprobar si existe la entrada de caché denominada `filecontents`:

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     Si la entrada de caché especificada no existe, debe leer el archivo de texto y agregarlo como una entrada de caché a la memoria caché.

6. En el bloque `if/then`, agregue el código siguiente para crear un nuevo objeto <xref:System.Runtime.Caching.CacheItemPolicy> que especifique que la entrada de caché expira después de 10 segundos.

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     Si no se proporciona ninguna información de expulsión o expiración, el valor predeterminado es <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, lo que significa que las entradas de caché nunca expiran en función de un tiempo absoluto. En su lugar, las entradas de la memoria caché expiran solo cuando hay presión de memoria. Como práctica recomendada, siempre debe proporcionar explícitamente una expiración absoluta o variable.

7. En el bloque `if/then` y siga el código que agregó en el paso anterior, agregue el código siguiente para crear una colección para las rutas de acceso de archivo que desea supervisar y para agregar la ruta de acceso del archivo de texto a la colección:

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    > Si el archivo de texto que desea usar no está `c:\cache\cacheText.txt`, especifique la ruta de acceso donde se encuentra el archivo de texto que desea utilizar.

8. Después del código que agregó en el paso anterior, agregue el código siguiente para agregar un nuevo objeto <xref:System.Runtime.Caching.HostFileChangeMonitor> a la colección de monitores de cambios para la entrada de caché:

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     El objeto <xref:System.Runtime.Caching.HostFileChangeMonitor> supervisa la ruta de acceso del archivo de texto y notifica a la memoria caché si se producen cambios. En este ejemplo, la entrada de la caché expirará si cambia el contenido del archivo.

9. Después del código que agregó en el paso anterior, agregue el código siguiente para leer el contenido del archivo de texto:

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     La marca de tiempo de fecha y hora se agrega para que pueda ver cuándo expira la entrada de caché.

10. Después del código que agregó en el paso anterior, agregue el código siguiente para insertar el contenido del archivo en el objeto de caché como una instancia de <xref:System.Runtime.Caching.CacheItem>:

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     Especifique información sobre cómo se debe expulsar la entrada de caché pasando el <xref:System.Runtime.Caching.CacheItemPolicy> objeto que creó anteriormente como parámetro.

11. Después del bloque `if/then`, agregue el código siguiente para mostrar el contenido del archivo almacenado en memoria caché en un cuadro de mensaje:

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. En el menú **compilar** , haga clic en **compilar WPFCaching** para compilar el proyecto.

## <a name="testing-caching-in-the-wpf-application"></a>Probar el almacenamiento en caché en la aplicación WPF
 Ahora puede probar la aplicación.

#### <a name="to-test-caching-in-the-wpf-application"></a>Para probar el almacenamiento en caché en la aplicación WPF

1. Presione CTRL+F5 para ejecutar la aplicación.

     Se muestra la ventana `MainWindow`.

2. Haga clic en **obtener caché**.

     El contenido almacenado en caché del archivo de texto se muestra en un cuadro de mensaje. Observe la marca de tiempo en el archivo.

3. Cierre el cuadro de mensaje y, a continuación, haga clic en **obtener caché** de nuevo.

     La marca de tiempo no cambia. Esto indica que se muestra el contenido almacenado en caché.

4. Espere 10 segundos o más y, a continuación, haga clic en **obtener caché** de nuevo.

     Esta vez se muestra una nueva marca de tiempo. Esto indica que la Directiva permite que la entrada de caché expire y que se muestre el nuevo contenido almacenado en caché.

5. En un editor de texto, abra el archivo de texto que creó. No realice ningún cambio todavía.

6. Cierre el cuadro de mensaje y, a continuación, haga clic en **obtener caché** de nuevo.

     Observe la marca de tiempo de nuevo.

7. Realice un cambio en el archivo de texto y, a continuación, guarde el archivo.

8. Cierre el cuadro de mensaje y, a continuación, haga clic en **obtener caché** de nuevo.

     Este cuadro de mensaje contiene el contenido actualizado del archivo de texto y una nueva marca de tiempo. Esto indica que el monitor de cambio de archivo de host expulsó la entrada de caché inmediatamente al cambiar el archivo, aunque el período de tiempo de espera absoluto no haya expirado.

    > [!NOTE]
    > Puede aumentar el tiempo de expulsión hasta 20 segundos o más para dejar más tiempo para que realice un cambio en el archivo.

## <a name="code-example"></a>Ejemplo de código
 Una vez que haya completado este tutorial, el código del proyecto que ha creado será similar al del ejemplo siguiente.

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [Almacenamiento en caché en aplicaciones .NET Framework](../../performance/caching-in-net-framework-applications.md)
