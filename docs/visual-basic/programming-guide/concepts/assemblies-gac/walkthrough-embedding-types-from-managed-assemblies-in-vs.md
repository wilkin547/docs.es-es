---
title: 'Tutorial: Incrustar los tipos de los ensamblados administrados en Visual Studio (Visual Basic) | Documentos de Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 56ed12ba-adff-4e9c-a668-7fcba80c4795
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: adc58e081cd9b874a841d84b11d92cbffb6ba6b8
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-visual-basic"></a>Tutorial: Incrustar los tipos de los ensamblados administrados en Visual Studio (Visual Basic)
Si incrusta información de tipos de un ensamblado administrado con nombre seguro, puede juntar tipos en una aplicación para conseguir la independencia de la versión. Es decir, el programa puede escribirse usar tipos de varias versiones de una biblioteca administrada sin tener que volver a compilarse para cada versión.  
  
 La incrustación de tipos se utiliza frecuentemente con la interoperabilidad COM, como una aplicación que usa objetos de automatización de Microsoft Office. Incrustar información de tipos permite la misma versión de un programa para trabajar con distintas versiones de Microsoft Office en equipos diferentes. Sin embargo, también puede usar la incrustación de tipos con una solución totalmente administrada.  
  
 Información de tipo se puede incrustar desde un ensamblado que tiene las siguientes características:  
  
-   El ensamblado expone al menos una interfaz pública.  
  
-   Las interfaces incrustadas se anotan con un `ComImport` atributo y un `Guid` atributo (y un GUID único).  
  
-   El ensamblado se anota con el `ImportedFromTypeLib` atributo o la `PrimaryInteropAssembly` atributo y un nivel de ensamblado `Guid` atributo. (De forma predeterminada, las plantillas de proyecto de Visual Basic incluyen un nivel de ensamblado `Guid` atributo.)  
  
 Después de especificar las interfaces públicas que se pueden incrustar, puede crear clases en tiempo de ejecución que implementan esas interfaces. Un programa cliente, a continuación, puede incrustar la información de tipo de dichas interfaces en tiempo de diseño haciendo referencia al ensamblado que contiene la configuración y las interfaces públicas la `Embed Interop Types` propiedad de la referencia a `True`. Esto es equivalente a utilizar el compilador de línea de comandos y hacer referencia al ensamblado utilizando el `/link` opción del compilador. El programa cliente, a continuación, puede cargar las instancias de los objetos en tiempo de ejecución de tipo esas interfaces. Si crea una nueva versión del ensamblado con nombre seguro en tiempo de ejecución, el programa cliente no necesario volver a compilar con el ensamblado actualizado en tiempo de ejecución. En su lugar, el programa cliente continúa utilizando cualquier versión del ensamblado en tiempo de ejecución está disponible, utilizando la información de tipo incrustada para las interfaces públicas.  
  
 Dado que la función principal de la incrustación de tipos es permitir la incrustación de información de tipos de ensamblados de interoperabilidad COM, se aplican las siguientes limitaciones al incrustar información de tipo en una solución totalmente administrada:  
  
-   Sólo los atributos específicos de interoperabilidad COM se incrustan; otros atributos se omiten.  
  
-   Si un tipo usa parámetros genéricos y el tipo del parámetro genérico es un tipo incrustado, ese tipo no se puede usar a través de un límite de ensamblado. Cruzar un límite de ensamblado ejemplos de llamar a un método desde otro ensamblado o un tipo de derivación de un tipo definido en otro ensamblado.  
  
-   Constantes no se incrustan.  
  
-   La <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>clase no admite un tipo incrustado como clave.</xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> Puede implementar su propio tipo de diccionario para admitir un tipo incrustado como clave.  
  
 En este tutorial, realizará lo siguiente:  
  
-   Crear un ensamblado con nombre seguro que tiene una interfaz pública que contiene información de tipo que se puede incrustar.  
  
-   Crear un ensamblado con nombre seguro en tiempo de ejecución que implementa esa interfaz pública.  
  
-   Crear un programa cliente que incrusta la información de tipo de la interfaz pública y crea una instancia de la clase del ensamblado en tiempo de ejecución.  
  
-   Modificar y volver a generar el ensamblado en tiempo de ejecución.  
  
-   Ejecute el programa de cliente para ver que se usa la nueva versión del ensamblado en tiempo de ejecución sin tener que volver a compilar el programa cliente.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="creating-an-interface"></a>Creación de una interfaz  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a>Para crear el proyecto de interfaz de equivalencia de tipos  
  
1.  En Visual Studio, en el **archivo** menú, seleccione **nueva** y, a continuación, haga clic en **proyecto**.  
  
2.  En el **nuevo proyecto** cuadro de diálogo el **tipos de proyecto** panel, asegúrese de que **Windows** está seleccionada. Seleccione **biblioteca de clases de** en el **plantillas** panel. En el **nombre** , escriba `TypeEquivalenceInterface`y, a continuación, haga clic en **Aceptar**. Se crea el nuevo proyecto.  
  
3.  En **el Explorador de soluciones**, haga clic en el archivo Class1.vb y haga clic en **cambiar el nombre de**. El nombre del archivo a `ISampleInterface.vb` y presione ENTRAR. Cambiar el nombre del archivo cambiará también la clase `ISampleInterface`. Esta clase representará la interfaz pública de la clase.  
  
4.  Haga clic en el proyecto TypeEquivalenceInterface y haga clic en **propiedades**. Haga clic en el **compilar** ficha. Establece la ruta de acceso de salida en una ubicación válida en el equipo de desarrollo, como `C:\TypeEquivalenceSample`. Esta ubicación también se usará en un paso posterior en este tutorial.  
  
5.  Mientras se siguen editando las propiedades del proyecto, haga clic en el **firma** ficha. Seleccione el **firmar el ensamblado** opción. En el **elegir un archivo de clave de nombre seguro** , haga clic ** <New...> **.</New...> En el **nombre de archivo de clave** , escriba `key.snk`. Desactive el **proteger mi archivo de clave con una contraseña** casilla de verificación. Haga clic en **Aceptar**.  
  
6.  Abra el archivo ISampleInterface.vb. Agregue el código siguiente al archivo de clase ISampleInterface para crear la interfaz ISampleInterface.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
7.  En el **herramientas** menú, haga clic en **crear Guid**. En el **crear GUID** cuadro de diálogo, haga clic en **formato del registro** y, a continuación, haga clic en **copia**. Haga clic en **Exit**.  
  
8.  En el `Guid` atributo, elimine el GUID de ejemplo y pegue el GUID que copió de la **crear GUID** cuadro de diálogo. Quite las llaves ({}) del GUID copiado.  
  
9. En el **proyecto** menú, haga clic en **mostrar todos los archivos**.  
  
10. En **el Explorador de soluciones**, expanda la **mi proyecto** carpeta. Haga doble clic en el AssemblyInfo.vb. Agregue el siguiente atributo al archivo.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
     Guarde el archivo.  
  
11. Guarde el proyecto.  
  
12. Haga clic en el proyecto TypeEquivalenceInterface y haga clic en **de compilación**. El archivo DLL de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada (por ejemplo, C:\TypeEquivalenceSample).  
  
## <a name="creating-a-runtime-class"></a>Creación de una clase en tiempo de ejecución  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a>Para crear el proyecto en tiempo de ejecución de equivalencia de tipos  
  
1.  En Visual Studio, en el **archivo** menú, seleccione **nueva** y, a continuación, haga clic en **proyecto**.  
  
2.  En el **nuevo proyecto** cuadro de diálogo el **tipos de proyecto** panel, asegúrese de que **Windows** está seleccionada. Seleccione **biblioteca de clases de** en el **plantillas** panel. En el **nombre** , escriba `TypeEquivalenceRuntime`y, a continuación, haga clic en **Aceptar**. Se crea el nuevo proyecto.  
  
3.  En **el Explorador de soluciones**, haga clic en el archivo Class1.vb y haga clic en **cambiar el nombre de**. El nombre del archivo a `SampleClass.vb` y presione ENTRAR. Cambiar el nombre también cambia el nombre de la clase `SampleClass`. Esta clase implementará la `ISampleInterface` interfaz.  
  
4.  Haga clic en el proyecto TypeEquivalenceRuntime y haga clic en **propiedades**. Haga clic en el **compilar** ficha. Establece la ruta de acceso de salida en la misma ubicación que se utilizó en el proyecto TypeEquivalenceInterface, por ejemplo, `C:\TypeEquivalenceSample`.  
  
5.  Mientras se siguen editando las propiedades del proyecto, haga clic en el **firma** ficha. Seleccione el **firmar el ensamblado** opción. En el **elegir un archivo de clave de nombre seguro** , haga clic ** <New...> **.</New...> En el **nombre de archivo de clave** , escriba `key.snk`. Desactive el **proteger mi archivo de clave con una contraseña** casilla de verificación. Haga clic en **Aceptar**.  
  
6.  Haga clic en el proyecto TypeEquivalenceRuntime y haga clic en **Agregar referencia**. Haga clic en el **examinar** ficha y vaya a la carpeta de la ruta de acceso de salida. Seleccione el archivo TypeEquivalenceInterface.dll y haga clic en **Aceptar**.  
  
7.  En el **proyecto** menú, haga clic en **mostrar todos los archivos**.  
  
8.  En **el Explorador de soluciones**, expanda la **referencias** carpeta. Seleccione la referencia TypeEquivalenceInterface. En la ventana Propiedades de la referencia TypeEquivalenceInterface, establezca la **versión específica** propiedad **False**.  
  
9. Agregue el código siguiente al archivo de clase SampleClass para crear la clase SampleClass.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
10. Guarde el proyecto.  
  
11. Haga clic en el proyecto TypeEquivalenceRuntime y haga clic en **de compilación**. El archivo DLL de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada (por ejemplo, C:\TypeEquivalenceSample).  
  
## <a name="creating-a-client-project"></a>Crear un proyecto de cliente  
  
#### <a name="to-create-the-type-equivalence-client-project"></a>Para crear el proyecto de cliente de equivalencia de tipos  
  
1.  En Visual Studio, en el **archivo** menú, seleccione **nueva** y, a continuación, haga clic en **proyecto**.  
  
2.  En el **nuevo proyecto** cuadro de diálogo el **tipos de proyecto** panel, asegúrese de que **Windows** está seleccionada. Seleccione **aplicación de consola** en el **plantillas** panel. En el **nombre** , escriba `TypeEquivalenceClient`y, a continuación, haga clic en **Aceptar**. Se crea el nuevo proyecto.  
  
3.  Haga clic en el proyecto TypeEquivalenceClient y haga clic en **propiedades**. Haga clic en el **compilar** ficha. Establece la ruta de acceso de salida en la misma ubicación que se utilizó en el proyecto TypeEquivalenceInterface, por ejemplo, `C:\TypeEquivalenceSample`.  
  
4.  Haga clic en el proyecto TypeEquivalenceClient y haga clic en **Agregar referencia**. Haga clic en el **examinar** ficha y vaya a la carpeta de la ruta de acceso de salida. Seleccione el archivo TypeEquivalenceInterface.dll (no TypeEquivalenceRuntime.dll) y haga clic en **Aceptar**.  
  
5.  En el **proyecto** menú, haga clic en **mostrar todos los archivos**.  
  
6.  En **el Explorador de soluciones**, expanda la **referencias** carpeta. Seleccione la referencia TypeEquivalenceInterface. En la ventana Propiedades de la referencia TypeEquivalenceInterface, establezca la **Embed Interop Types** propiedad **True**.  
  
7.  Agregue el código siguiente al archivo Module1.vb para crear el programa cliente.  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
8.  Presione CTRL + F5 para compilar y ejecutar el programa.  
  
## <a name="modifying-the-interface"></a>Modificación de la interfaz  
  
#### <a name="to-modify-the-interface"></a>Para modificar la interfaz  
  
1.  En Visual Studio, en el **archivo** menú, seleccione **abiertos**y, a continuación, haga clic en **proyecto o solución**.  
  
2.  En el **Abrir proyecto** cuadro de diálogo, haga clic en el proyecto TypeEquivalenceInterface y, a continuación, haga clic en **propiedades**. Haga clic en la pestaña **Aplicación** . Haga clic en el **información de ensamblado** botón. Cambiar el **versión de ensamblado** y **versión** valores `2.0.0.0`.  
  
3.  Abra el archivo ISampleInterface.vb. Agregue la siguiente línea de código a la interfaz ISampleInterface.  
  
<CodeContentPlaceHolder>4</CodeContentPlaceHolder>  
     Guarde el archivo.  
  
4.  Guarde el proyecto.  
  
5.  Haga clic en el proyecto TypeEquivalenceInterface y haga clic en **de compilación**. Una nueva versión del archivo .dll de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada (por ejemplo, C:\TypeEquivalenceSample).  
  
## <a name="modifying-the-runtime-class"></a>Modificar la clase en tiempo de ejecución  
  
#### <a name="to-modify-the-runtime-class"></a>Para modificar la clase en tiempo de ejecución  
  
1.  En Visual Studio, en el **archivo** menú, seleccione **abiertos**y, a continuación, haga clic en **proyecto o solución**.  
  
2.  En el **Abrir proyecto** cuadro de diálogo, haga clic en el proyecto TypeEquivalenceRuntime y haga clic en **propiedades**. Haga clic en la pestaña **Aplicación** . Haga clic en el **información de ensamblado** botón. Cambiar el **versión de ensamblado** y **versión** valores `2.0.0.0`.  
  
3.  Abra la SampleClass.vbfile. Agregue las siguientes líneas de código a la clase SampleClass.  
  
```vb  
Public Function GetDate() As DateTime Implements ISampleInterface.GetDate  
    Return Now  
End Function  
```  
  
     Save the file.  
  
4.  Guarde el proyecto.  
  
5.  Haga clic en el proyecto TypeEquivalenceRuntime y haga clic en **de compilación**. Una versión actualizada del archivo .dll de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada anteriormente (por ejemplo, C:\TypeEquivalenceSample).  
  
6.  En el Explorador de archivos, abra la carpeta de la ruta de acceso de salida (por ejemplo, C:\TypeEquivalenceSample). Haga doble clic en TypeEquivalenceClient.exe para ejecutar el programa. El programa reflejará la nueva versión del ensamblado TypeEquivalenceRuntime sin haberse compilado de nuevo.  
  
## <a name="see-also"></a>Vea también  
 [/Link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)   
 [Conceptos de programación](../../../../visual-basic/programming-guide/concepts/index.md)   
 [Programar con ensamblados](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6)   
 [Ensamblados y caché Global de ensamblados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)

