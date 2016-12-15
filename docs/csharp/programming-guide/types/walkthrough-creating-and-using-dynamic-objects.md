---
title: "Tutorial: Crear y utilizar objetos din&#225;micos (C# y Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "objetos dinámicos"
  - "objetos dinámicos [C#]"
  - "objetos dinámicos [Visual Basic]"
ms.assetid: 568f1645-1305-4906-8625-5d77af81e04f
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Tutorial: Crear y utilizar objetos din&#225;micos (C# y Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Los objetos dinámicos exponen miembros como propiedades y métodos en tiempo de ejecución, en lugar de en tiempo de compilación.  Esto permite crear objetos para trabajar con estructuras que no coinciden con un tipo o formato estático.  Por ejemplo, puede utilizar un objeto dinámico para hacer referencia al Modelo de objeto del documento HTML \(DOM\), que puede contener cualquier combinación de elementos y atributos HTML válidos.  Dado que cada documento HTML es único, se determinan los miembros del documento en tiempo de ejecución.  Un método habitual de hacer referencia a un atributo de un elemento XHTML consiste en pasar el nombre del atributo al método `GetProperty` del elemento.  Para hacer referencia al atributo `id` del elemento HTML `<div id="Div1">`, primero hay que obtener una referencia al elemento `<div>` y, a continuación, utilizar `divElement.GetProperty("id")`.  Si utiliza un objeto dinámico, puede hacer referencia al atributo `id` como `divElement.id`.  
  
 Los objetos dinámicos también proporcionan acceso más cómodo a los lenguajes dinámicos, como IronPython e IronRuby.  Puede usar un objeto dinámico para hacer referencia a un script dinámico que se interpreta en tiempo de ejecución.  
  
 Para hacer referencia a un objeto dinámico se puede usar el enlace en tiempo de ejecución.  En C\#, se especifica el tipo de un objeto enlazado en tiempo de ejecución como `dynamic`.  En [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], se especifica el tipo de un objeto enlazado en tiempo de ejecución como `Object`.  Para obtener más información, vea [dynamic](../../../csharp/language-reference/keywords/dynamic.md) y [Enlace en tiempo de compilación y en tiempo de ejecución](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md).  
  
 Puede crear objetos dinámicos personalizados utilizando las clases del espacio de nombres <xref:System.Dynamic?displayProperty=fullName>.  Por ejemplo, puede crear <xref:System.Dynamic.ExpandoObject> y especificar los miembros de ese objeto en tiempo de ejecución.  También puede crear un tipo que herede la clase <xref:System.Dynamic.DynamicObject>.  Después puede reemplazar los miembros de la clase <xref:System.Dynamic.DynamicObject> para proporcionar la funcionalidad dinámica en tiempo de ejecución.  
  
 En este tutorial realizará las tareas siguientes:  
  
-   Crear un objeto personalizado que expone dinámicamente al contenido de un archivo de texto como propiedades de un objeto.  
  
-   Cree un proyecto que use una biblioteca de `IronPython`.  
  
## Requisitos previos  
 Para poder completar este tutorial, necesita IronPython 2.6.1 para .NET Framework 4.  Puede descargar IronPython 2.6.1 para .NET Framework 4 de [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187223).  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## Crear un objeto dinámico personalizado  
 En el primer proyecto que se crea en este tutorial se define un objeto dinámico personalizado que busca en el contenido de un archivo de texto.  El nombre de una propiedad dinámica especifica el texto que hay que buscar.  Por ejemplo, si el código de llamada especifica `dynamicFile.Sample`, la clase dinámica devuelve una lista genérica de cadenas que contiene todas las líneas del archivo que comienzan con "Sample".  La búsqueda no distingue entre mayúsculas y minúsculas.  La clase dinámica también admite dos argumentos opcionales.  El primer argumento es un valor enum de la opción de búsqueda que especifica que la clase dinámica debería buscar las coincidencias en el inicio, en el final o en cualquier parte de la línea.  El segundo argumento especifica que la clase dinámica debería recortar los espacios iniciales y finales de cada línea antes de buscar.  Por ejemplo, si el código de llamada especifica `dynamicFile.Sample(StringSearchOption.Contains)`, la clase dinámica busca "Sample" en cualquier parte de una línea.  Si el código de llamada especifica `dynamicFile.Sample(StringSearchOption.StartsWith, false)`, la clase dinámica busca "Sample" en el inicio de cada línea y no quita los espacios iniciales y finales.  El comportamiento predeterminado de la clase dinámica es buscar una coincidencia en el inicio de cada línea y quitar los espacios iniciales y finales.  
  
#### Para crear una clase dinámica personalizada  
  
1.  Inicie [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].  
  
2.  En el menú **Archivo**, elija **Nuevo** y haga clic en **Proyecto**.  
  
3.  En el cuadro de diálogo **Nuevo proyecto**, en el panel **Tipos de proyecto**, asegúrese de haber seleccionado **Windows**.  En el panel **Plantillas**, seleccione **Aplicación de consola**.  En el cuadro **Nombre**, escriba `DynamicSample` y, a continuación, haga clic en **Aceptar**.  Se crea el nuevo proyecto.  
  
4.  Haga clic con el botón secundario en el proyecto DynamicSample, señale **Agregar** y haga clic en **Clase**.  En el cuadro **Nombre**, escriba `ReadOnlyFile` y, a continuación, haga clic en **Aceptar**.  Se agrega un nuevo archivo que contiene la clase ReadOnlyFile.  
  
5.  En la parte superior del archivo ReadOnlyFile.cs o ReadOnlyFile.vb, agregue el siguiente código para importar los espacios de nombres <xref:System.Dynamic?displayProperty=fullName> y <xref:System.IO?displayProperty=fullName>.  
  
     [!code-cs[VbDynamicWalkthrough#1](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_1.cs)]
     [!code-vb[VbDynamicWalkthrough#1](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_1.vb)]  
  
6.  El objeto dinámico personalizado utiliza una enumeración para determinar el criterio de búsqueda.  Antes de la instrucción de clase, agregue la siguiente definición de enumeración.  
  
     [!code-cs[VbDynamicWalkthrough#2](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_2.cs)]
     [!code-vb[VbDynamicWalkthrough#2](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_2.vb)]  
  
7.  Actualice la instrucción de clase que herede la clase `DynamicObject`, como se muestra en el siguiente ejemplo de código.  
  
     [!code-cs[VbDynamicWalkthrough#3](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_3.cs)]
     [!code-vb[VbDynamicWalkthrough#3](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_3.vb)]  
  
8.  Agregue el código siguiente a la clase `ReadOnlyFile` para definir un campo privado para la ruta de archivo y un constructor para la clase `ReadOnlyFile`.  
  
     [!code-cs[VbDynamicWalkthrough#4](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_4.cs)]
     [!code-vb[VbDynamicWalkthrough#4](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_4.vb)]  
  
9. Agregue el método `GetPropertyValue` a la clase `ReadOnlyFile`.  El método `GetPropertyValue` toma como entrada los criterios de búsqueda y devuelve las líneas de un archivo de texto que coinciden con el criterio de búsqueda.  Los métodos dinámicos proporcionados por la clase `ReadOnlyFile` llaman al método `GetPropertyValue` para recuperar los resultados respectivos.  
  
     [!code-cs[VbDynamicWalkthrough#5](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_5.cs)]
     [!code-vb[VbDynamicWalkthrough#5](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_5.vb)]  
  
10. Después del método `GetPropertyValue`, agregue el código siguiente para reemplazar el método <xref:System.Dynamic.DynamicObject.TryGetMember%2A> de la clase <xref:System.Dynamic.DynamicObject>.  Se llama al método <xref:System.Dynamic.DynamicObject.TryGetMember%2A> cuando se solicita un miembro de una clase dinámica y no se especifica ningún argumento.  El argumento `binder` contiene información sobre el miembro al que se ha hecho referencia y el argumento `result` hace referencia al resultado devuelto para el miembro especificado.  El método <xref:System.Dynamic.DynamicObject.TryGetMember%2A> devuelve un valor booleano que devuelve `true` si el miembro solicitado existe; de lo contrario devuelve `false`.  
  
     [!code-cs[VbDynamicWalkthrough#6](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_6.cs)]
     [!code-vb[VbDynamicWalkthrough#6](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_6.vb)]  
  
11. Después del método `TryGetMember`, agregue el código siguiente para reemplazar el método <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> de la clase <xref:System.Dynamic.DynamicObject>.  Se llama al método <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> cuando un miembro de una clase dinámica se solicita con argumentos.  El argumento `binder` contiene información sobre el miembro al que se ha hecho referencia y el argumento `result` hace referencia al resultado devuelto para el miembro especificado.  El argumento `args` contiene una matriz de argumentos que se pasan al miembro.  El método <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> devuelve un valor booleano que devuelve `true` si el miembro solicitado existe; de lo contrario devuelve `false`.  
  
     La versión personalizada del método `TryInvokeMember` espera el que primer argumento sea un valor de la enumeración `StringSearchOption` que definió en un paso anterior.  El método `TryInvokeMember` espera que el segundo argumento sea un valor booleano.  Si uno o ambos argumentos son valores válidos, se pasan al método `GetPropertyValue` para recuperar los resultados.  
  
     [!code-cs[VbDynamicWalkthrough#7](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_7.cs)]
     [!code-vb[VbDynamicWalkthrough#7](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_7.vb)]  
  
12. Guarde y cierre el archivo.  
  
#### Para crear un archivo de texto de muestra  
  
1.  Haga clic con el botón secundario en el proyecto DynamicSample, señale **Agregar** y haga clic en **Nuevo elemento**.  En el panel **Plantillas instaladas**, seleccione **General** y, a continuación, seleccione la plantilla **Archivo de texto**.  Deje el nombre predeterminado de TextFile1.txt en el cuadro **Nombre** y haga clic en **Agregar**.  Se agregará un nuevo archivo de texto al proyecto.  
  
2.  Copie el siguiente texto en el archivo TextFile1.txt.  
  
    ```  
    List of customers and suppliers  
  
    Supplier: Lucerne Publishing (http://www.lucernepublishing.com/)  
    Customer: Preston, Chris  
    Customer: Hines, Patrick  
    Customer: Cameron, Maria  
    Supplier: Graphic Design Institute (http://www.graphicdesigninstitute.com/)   
    Supplier: Fabrikam, Inc. (http://www.fabrikam.com/)   
    Customer: Seubert, Roxanne  
    Supplier: Proseware, Inc. (http://www.proseware.com/)   
    Customer: Adolphi, Stephan  
    Customer: Koch, Paul  
    ```  
  
3.  Guarde y cierre el archivo.  
  
#### Para crear una aplicación de ejemplo que utiliza el objeto dinámico personalizado  
  
1.  En el **Explorador de soluciones**, haga doble clic en el archivo Module1.vb si está utilizando [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] o el archivo Program.cs si utiliza Visual C\#.  
  
2.  Agregue el siguiente código al procedimiento Main para crear una instancia de la clase `ReadOnlyFile` para el archivo TextFile1.txt.  El código utiliza el enlace en tiempo de ejecución para llamar a los miembros dinámicos y recuperar líneas de texto que contienen la cadena "Customer".  
  
     [!code-cs[VbDynamicWalkthrough#8](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_8.cs)]
     [!code-vb[VbDynamicWalkthrough#8](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_8.vb)]  
  
3.  Guarde el archivo y presione CTRL\+F5 para compilar y ejecutar la aplicación.  
  
## Llamar a una biblioteca de lenguaje dinámico  
 El proyecto siguiente que se crea en este tutorial obtiene acceso a una biblioteca escrita en el lenguaje dinámico IronPython.  Para crear este proyecto, debe tener instalado IronPython 2.6.1 para .NET Framework 4.  Puede descargar IronPython 2.6.1 para .NET Framework 4 de [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187223).  
  
#### Para crear una clase dinámica personalizada  
  
1.  En el menú **Archivo** de [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], seleccione **Nuevo** y haga clic en **Proyecto**.  
  
2.  En el cuadro de diálogo **Nuevo proyecto**, en el panel **Tipos de proyecto**, asegúrese de haber seleccionado **Windows**.  En el panel **Plantillas**, seleccione **Aplicación de consola**.  En el cuadro **Nombre**, escriba `DynamicIronPythonSample` y haga clic en **Aceptar**.  Se crea el nuevo proyecto.  
  
3.  Si usa [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], haga clic con el botón secundario en el proyecto DynamicIronPythonSample y, a continuación, haga clic en **Propiedades**.  Haga clic en la ficha **Referencias**.  Haga clic en el botón **Agregar**.  Si usa Visual C\#, en el **Explorador de soluciones**, haga clic con el botón secundario en la carpeta **Referencias** y, a continuación, haga clic en **Agregar referencia**.  
  
4.  En la pestaña **Examinar**, busque la carpeta donde están instaladas las bibliotecas de IronPython.  Por ejemplo, C:\\Archivos de programa\\IronPython 2.6 para .NET Framework 4.  Seleccione las bibliotecas **IronPython.dll**, **IronPython.Modules.dll**, **Microsoft.Scripting.dll** y **Microsoft.Dynamic.dll**.  Haga clic en **Aceptar**.  
  
5.  Si usa [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], modifique el archivo Module1.vb.  Si usa Visual C\#, modifique el archivo Program.cs.  
  
6.  En la parte superior del archivo, agregue el código siguiente para importar los espacios de nombres `Microsoft.Scripting.Hosting` y `IronPython.Hosting` de las bibliotecas de IronPython.  
  
     [!code-cs[VbDynamicWalkthroughIronPython#1](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_9.cs)]
     [!code-vb[VbDynamicWalkthroughIronPython#1](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_9.vb)]  
  
7.  En el método Main, agregue el código siguiente para crear un nuevo objeto `Microsoft.Scripting.Hosting.ScriptRuntime` para hospedar las bibliotecas de IronPython.  El objeto `ScriptRuntime` carga el módulo random.py de la biblioteca de IronPython.  
  
     [!code-cs[VbDynamicWalkthroughIronPython#2](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_10.cs)]
     [!code-vb[VbDynamicWalkthroughIronPython#2](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_10.vb)]  
  
8.  Después de que el código cargue el módulo random.py, agregue el código siguiente para crear una matriz de enteros.  La matriz se pasa al método `shuffle` del módulo random.py, que ordena los valores de la matriz de forma aleatoria.  
  
     [!code-cs[VbDynamicWalkthroughIronPython#3](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_11.cs)]
     [!code-vb[VbDynamicWalkthroughIronPython#3](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_11.vb)]  
  
9. Guarde el archivo y presione CTRL\+F5 para compilar y ejecutar la aplicación.  
  
## Vea también  
 <xref:System.Dynamic?displayProperty=fullName>   
 <xref:System.Dynamic.DynamicObject?displayProperty=fullName>   
 [Uso de tipo dinámico](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [Enlace en tiempo de compilación y en tiempo de ejecución](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [Implementar las interfaces dinámicas \(blog externo\)](http://go.microsoft.com/fwlink/?LinkId=230895)