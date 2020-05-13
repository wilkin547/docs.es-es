---
title: Localizar una aplicación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: dc7d8f4f56b26fffbd883e1e1d6e420026e1f94f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209687"
---
# <a name="how-to-localize-an-application"></a>Cómo: localizar una aplicación

En este tutorial se explica cómo crear una aplicación localizada mediante la herramienta LocBaml.  
  
> [!NOTE]
> La herramienta LocBaml no es una aplicación lista para producción. Se presenta como un ejemplo que usa algunas de las API de localización y muestra cómo se podría escribir una herramienta de localización.  
  
## <a name="overview"></a>Información general

En este artículo se ofrece un enfoque paso a paso para localizar una aplicación. En primer lugar, prepare la aplicación para que se pueda extraer el texto que se va a traducir. Una vez traducido el texto, combine el texto traducido en una nueva copia de la aplicación original.
  
## <a name="create-a-sample-application"></a>Creación de una aplicación de ejemplo

En este paso, va a preparar la aplicación para la localización. En los ejemplos de Windows Presentation Foundation (WPF), se proporciona un ejemplo de HelloApp que se usará para los ejemplos de código de este debate. Si desea usar este ejemplo, descargue los archivos lenguaje XAML (XAML) del ejemplo de la [herramienta LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).  
  
1. Desarrolle su aplicación hasta el punto donde desea iniciar la localización.  
  
2. Especifique el lenguaje de desarrollo en el archivo de proyecto para que MSBuild genere un ensamblado principal y un ensamblado satélite (un archivo con la extensión. Resources. dll) para que contenga los recursos de idioma neutro. El archivo de proyecto en el ejemplo HelloApp es HelloApp.csproj. En ese archivo, encontrará el lenguaje de desarrollo que se identifica como sigue:  
  
   `<UICulture>en-US</UICulture>`  
  
3. Agregue UID a los archivos XAML. Los UID se usan para realizar un seguimiento de los cambios en los archivos y para identificar los elementos que se deben traducir. Para agregar UID a los archivos, ejecute `updateuid` en el archivo del proyecto:  

   `msbuild -t:updateuid helloapp.csproj`

   Para comprobar que no faltan UID ni están duplicados, ejecute `checkuid` :  

   `msbuild -t:checkuid helloapp.csproj`

   Después de ejecutar `updateuid` , los archivos deben contener UID. Por ejemplo, en el archivo *Pane1. Xaml* de HelloApp, debería encontrar lo siguiente:  

   ```xaml
   <StackPanel x:Uid="StackPanel_1">
     <TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>
     <TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>
   </StackPanel>
   ```

## <a name="create-the-neutral-language-resources-satellite-assembly"></a>Crear el ensamblado satélite de recursos de idioma neutro

Después de configurar la aplicación para que genere un ensamblado satélite de recursos de idioma neutro, compile la aplicación. Esto genera el ensamblado de aplicación principal, así como el ensamblado satélite de recursos de idioma neutro que LocBaml necesita para la localización.

Para compilar la aplicación:  
  
1. Compile HelloApp para crear una biblioteca de vínculos dinámicos (DLL):  
  
   `msbuild helloapp.csproj`
  
2. El ensamblado de aplicación principal que se acaba de crear, HelloApp. exe, se crea en la siguiente carpeta: *C:\HelloApp\Bin\Debug*
  
3. El ensamblado satélite de recursos de idioma neutro que se acaba de crear, HelloApp. Resources. dll, se crea en la siguiente carpeta: *C:\HelloApp\Bin\Debug\en-US*
  
## <a name="build-the-locbaml-tool"></a>Compilar la herramienta LocBaml  
  
1. Todos los archivos necesarios para compilar LocBaml se encuentran en los ejemplos de WPF. Descargue los archivos de C# del [ejemplo de la herramienta LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).  
  
2. Desde la línea de comandos, ejecute el archivo de proyecto (locbaml.csproj) para compilar la herramienta:  

   `msbuild locbaml.csproj`
  
3. Vaya al directorio *Bin\Release* para buscar el archivo ejecutable recién creado (LocBaml. exe). Ejemplo: *C:\LocBaml\Bin\Release\locbaml.exe*
  
4. Las opciones que puede especificar al ejecutar LocBaml son las siguientes.

   | Opción | Descripción|
   | - | - |
   | `parse` o `-p` | Analiza los archivos BAML, Resources o DLL para generar un archivo. csv o. txt. |
   | `generate` o `-g` | Genera un archivo binario localizado mediante un archivo traducido. |
   | `out`o `-o` {*filedirectory*] | Nombre del archivo de salida. |
   | `culture`o `-cul` {*Culture*] | Configuración regional de los ensamblados de salida. |
   | `translation`o `-trans` {*Translation. csv*] | Archivo traducido o localizado. |
   | `asmpath`o `-asmpath` {*filedirectory*] | Si el código XAML contiene controles personalizados, debe proporcionar `asmpath` al ensamblado del control personalizado. |
   | `nologo` |  no muestra un logotipo ni información de copyright. |
   | `verbose` |  muestra información en modo detallado. |
  
   > [!NOTE]
   > Si necesita una lista de las opciones cuando ejecute la herramienta, escriba `LocBaml.exe` y, a continuación, presione **entrar**.
  
## <a name="use-locbaml-to-parse-a-file"></a>Usar LocBaml para analizar un archivo

Ahora que ya ha creado la herramienta LocBaml, está listo para usarla para analizar HelloApp.resources.dll y extraer el contenido de texto que se traducirá.  
  
1. Copie LocBaml.exe en la carpeta bin\debug de la aplicación, que es donde se creó el ensamblado de aplicación principal.  
  
2. Para analizar el archivo de ensamblado satélite y almacenar la salida como un archivo .csv, use el siguiente comando:  
  
   `LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv`
  
   > [!NOTE]
   > Si el archivo de entrada, HelloApp.resources.dll, no está en el mismo directorio que LocBaml.exe, mueva uno de los archivos para que ambos archivos se encuentren en el mismo directorio.  
  
3. Cuando se ejecuta LocBaml para analizar los archivos, la salida se compone de siete campos delimitados por comas (archivos .csv) o tabuladores (archivos .txt). A continuación se muestra el archivo .csv analizado para HelloApp.resources.dll:

   | |
   |-|
   |HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;|
   |HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World|
   |HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World|

   Los siete campos son:  
  
   - **Nombre BAML**. Es el nombre del recurso BAML con respecto al ensamblado satélite de lenguaje de origen.  
  
   - **Clave de recurso**. Es el identificador de recursos localizado.  
  
   - **Categoría**. Tipo de valor. Vea [atributos y comentarios de localización](localization-attributes-and-comments.md).  
  
   - **Legibilidad**. Indica si un localizador puede leer el valor. Vea [atributos y comentarios de localización](localization-attributes-and-comments.md).  
  
   - **Modificabilidad**. Indica si un localizador puede modificar el valor. Vea [atributos y comentarios de localización](localization-attributes-and-comments.md).  
  
   - **Comentarios**. Descripción adicional del valor para ayudar a determinar cómo se localiza. Vea [atributos y comentarios de localización](localization-attributes-and-comments.md).  
  
   - **Valor**. Es el valor de texto que se va a traducir a la referencia cultural deseada.  
  
   En la tabla siguiente se muestra la correspondencia entre estos campos y los valores delimitados del archivo CSV:  
  
   |Nombre de BAML|Clave del recurso|Category|Legibilidad|Modificabilidad|Comentarios|Valor|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |HelloApp.g.en-US.resources:window1.baml|Stack1:System.Windows.Controls.StackPanel.$Content|Ignore|FALSE|FALSE||#Text1;#Text2|
   |HelloApp.g.en-US.resources:window1.baml|Text1:System.Windows.Controls.TextBlock.$Content|None|TRUE|TRUE||Hello World|
   |HelloApp.g.en-US.resources:window1.baml|Text2:System.Windows.Controls.TextBlock.$Content|None|TRUE|TRUE||Goodbye World|
  
   Observe que todos los valores del campo **comentarios** no contienen valores; Si un campo no tiene un valor, está vacío. Observe también que el elemento de la primera fila no es legible ni modificable y tiene "ignore" como su valor de **categoría** , lo que indica que el valor no es localizable.  
  
4. Para facilitar la detección de los elementos localizables en los archivos analizados, especialmente en los archivos de gran tamaño, puede ordenar o filtrar los elementos por **categoría**, **legibilidad**y **modificabilidad**. Por ejemplo, puede filtrar los valores ilegibles y no modificables.  
  
## <a name="translate-the-localizable-content"></a>Traducir el contenido localizable

Use cualquier herramienta disponible traducir el contenido extraído. Una buena forma de hacerlo es escribir los recursos en un archivo. csv y verlos en Microsoft Excel, realizando cambios de traducción en la última columna (valor).  
  
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a>Usar LocBaml para generar un nuevo archivo. Resources. dll

El contenido que se identificó al analizar HelloApp.resources.dll con LocBaml se ha traducido y debe combinarse en la aplicación original. Use la `generate` `-g` opción o para generar un nuevo archivo. Resources. dll.  
  
1. Use la sintaxis siguiente para generar un nuevo archivo HelloApp.resources.dll. Marque la referencia cultural como en-US (/cul:en-US).  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US`  

   > [!NOTE]
   > Si el archivo de entrada, Hello.csv, no está en el mismo directorio que el ejecutable, LocBaml.exe, mueva uno de los archivos para que ambos se encuentren en el mismo directorio.  
  
2. Reemplace el archivo *HelloApp. Resources. dll* anterior en el directorio *C:\HelloApp\Bin\Debug\en-US\HelloApp.Resources.dll* por el archivo *HelloApp. Resources. dll* recién creado.  
  
3. “Hello World” y “Goodbye World” deberían aparecer ya traducidos en la aplicación.  
  
4. Para traducir a una referencia cultural diferente, use la referencia cultural del idioma al que va a traducir. En el ejemplo siguiente se muestra cómo traducir al francés canadiense:  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA`  
  
5. En el mismo ensamblado que el ensamblado de aplicación principal, cree una nueva carpeta específica de la referencia cultural para alojar el nuevo ensamblado satélite. Para el francés canadiense, la carpeta sería fr-CA.  
  
6. Copie el ensamblado satélite generado en la nueva carpeta.  
  
7. Para probar el nuevo ensamblado satélite, deberá cambiar la referencia cultural en la que se ejecutará la aplicación. Puede hacerlo de una de las maneras siguientes:  
  
   - Cambiar la configuración regional del sistema operativo.
  
   - En la aplicación, agregue el código siguiente a App.xaml.cs:  
  
     [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
     [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
     [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
## <a name="tips-for-using-locbaml"></a>Sugerencias para usar LocBaml  
  
- Todos los ensamblados dependientes que definen controles personalizados se deben copiar en el directorio local de LocBaml o instalarse en la GAC (caché global de ensamblados). Esto es necesario porque la API de localización debe tener acceso a los ensamblados dependientes cuando lee el XAML binario (BAML).  
  
- Si el ensamblado principal está firmado, la DLL de recursos generada también debe estar firmada para que se pueda cargar.  
  
- La versión de la DLL de recursos localizados debe estar sincronizada con el ensamblado principal.
  
## <a name="see-also"></a>Consulte también

- [Globalización de WPF](globalization-for-wpf.md)
- [Información general sobre el uso del diseño automático](use-automatic-layout-overview.md)
