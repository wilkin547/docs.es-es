---
title: 'Tutorial: Crear y usar objetos dinámicos (C# y Visual Basic)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dynamic objects [Visual Basic]
- dynamic objects
- dynamic objects [C#]
ms.assetid: 568f1645-1305-4906-8625-5d77af81e04f
ms.openlocfilehash: 3b5a92948a3e692a734f3ddee3c7238d5d27588f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79157057"
---
# <a name="walkthrough-creating-and-using-dynamic-objects-c-and-visual-basic"></a>Tutorial: Crear y usar objetos dinámicos (C# y Visual Basic)

Los objetos dinámicos exponen miembros como propiedades y métodos en tiempo de ejecución, en lugar de en tiempo de compilación. Esto le permite crear objetos para trabajar con estructuras que no coinciden con un formato o tipo estático. Por ejemplo, puede usar un objeto dinámico para hacer referencia a Document Object Model (DOM) HTML, que puede contener cualquier combinación de atributos y elementos de marcado HTML válidos. Dado que cada documento HTML es único, los miembros de un documento HTML específico se determinan en tiempo de ejecución. Un método común para hacer referencia a un atributo de un elemento HTML consiste en pasar el nombre del atributo al método `GetProperty` del elemento. Para hacer referencia al atributo `id` del elemento HTML `<div id="Div1">`, primero debe obtener una referencia al elemento `<div>` y, después, usar `divElement.GetProperty("id")`. Si usa un objeto dinámico, puede hacer referencia al atributo `id` como `divElement.id`.  
  
 Los objetos dinámicos también proporcionan un acceso cómodo a lenguajes dinámicos como IronPython e IronRuby. Puede usar un objeto dinámico para hacer referencia a un script dinámico que se interpreta en tiempo de ejecución.  
  
 Para hacer referencia a un objeto dinámico, use un enlace en tiempo de ejecución. En C#, el tipo de un objeto enlazado en tiempo de ejecución se especifica como `dynamic`. En Visual Basic, el tipo de un objeto enlazado en tiempo de ejecución se especifica como `Object`. Para obtener más información, vea [dynamic](../../language-reference/builtin-types/reference-types.md) y [Enlace en tiempo de compilación y en tiempo de ejecución](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).  
  
 Puede crear objetos dinámicos personalizados con las clases del espacio de nombres <xref:System.Dynamic?displayProperty=nameWithType>. Por ejemplo, puede crear un objeto <xref:System.Dynamic.ExpandoObject> y especificar los miembros de ese objeto en tiempo de ejecución. También puede crear su propio tipo que hereda la clase <xref:System.Dynamic.DynamicObject>. Después, puede invalidar los miembros de la clase <xref:System.Dynamic.DynamicObject> para proporcionar funciones dinámicas en tiempo de ejecución.  
  
 En este tutorial realizará las tareas siguientes:  
  
- Crear un objeto personalizado que expone dinámicamente el contenido de un archivo de texto como propiedades de un objeto.  
  
- Crear un proyecto que usa una biblioteca `IronPython`.  
  
## <a name="prerequisites"></a>Requisitos previos  

Necesita [IronPython](https://ironpython.net/) para .NET para poder seguir este tutorial. Vaya a su [página de descarga](https://ironpython.net/download/) para obtener la versión más reciente.
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-a-custom-dynamic-object"></a>Crear un objeto dinámico personalizado

El primer proyecto que se crea en este tutorial define un objeto dinámico personalizado que busca en el contenido de un archivo de texto. El texto que se va a buscar se especifica mediante el nombre de una propiedad dinámica. Por ejemplo, si el código de llamada especifica `dynamicFile.Sample`, la clase dinámica devuelve una lista genérica de cadenas que contiene todas las líneas del archivo que comienzan con "Sample". La búsqueda no distingue entre mayúsculas y minúsculas. La clase dinámica también admite dos argumentos opcionales. El primer argumento es un valor de enumeración de opción de búsqueda que especifica que la clase dinámica debe buscar coincidencias al principio de la línea, al final de la línea o en cualquier parte de la línea. El segundo argumento especifica que la clase dinámica debe recortar los espacios iniciales y finales de cada línea antes de buscar. Por ejemplo, si el código de llamada especifica `dynamicFile.Sample(StringSearchOption.Contains)`, la clase dinámica busca "Sample" en cualquier parte de una línea. Si el código de llamada especifica `dynamicFile.Sample(StringSearchOption.StartsWith, false)`, la clase dinámica busca "Sample" al principio de cada línea y no quita los espacios iniciales y finales. El comportamiento predeterminado de la clase dinámica es buscar una coincidencia al principio de cada línea y quitar los espacios iniciales y finales.  
  
### <a name="to-create-a-custom-dynamic-class"></a>Para crear una clase dinámica personalizada  
  
1. Inicie Visual Studio.  
  
2. En el menú **Archivo** , elija **Nuevo** y haga clic en **Proyecto**.  
  
3. En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**. Seleccione **Aplicación de consola** en el panel **Plantillas**. En el cuadro **Nombre**, escriba `DynamicSample` y haga clic en **Aceptar**. Se crea el proyecto.  
  
4. Haga clic con el botón derecho en el proyecto DynamicSample, seleccione **Agregar** y, después, haga clic en **Clase**. En el cuadro **Nombre**, escriba `ReadOnlyFile` y haga clic en **Aceptar**. Se agrega un nuevo archivo que contiene la clase ReadOnlyFile.  
  
5. En la parte superior del archivo ReadOnlyFile.cs o ReadOnlyFile.vb, agregue el código siguiente para importar los espacios de nombres <xref:System.IO?displayProperty=nameWithType> y <xref:System.Dynamic?displayProperty=nameWithType>.  

    [!code-csharp[VbDynamicWalkthrough#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#1)]
    [!code-vb[VbDynamicWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#1)]  

6. El objeto dinámico personalizado usa una enumeración para determinar los criterios de búsqueda. Antes de la instrucción de clase, agregue la siguiente definición de enumeración.  
  
    [!code-csharp[VbDynamicWalkthrough#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#2)]
    [!code-vb[VbDynamicWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#2)]
  
7. Actualice la instrucción de clase para heredar la clase `DynamicObject`, como se muestra en el ejemplo de código siguiente.  
  
    [!code-csharp[VbDynamicWalkthrough#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#3)]
    [!code-vb[VbDynamicWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#3)]

8. Agregue el código siguiente a la clase `ReadOnlyFile` para definir un campo privado para la ruta de acceso y un constructor para la clase `ReadOnlyFile`.  
  
    [!code-csharp[VbDynamicWalkthrough#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#4)]
    [!code-vb[VbDynamicWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#4)]
  
9. Agregue el método `GetPropertyValue` siguiente a la clase `ReadOnlyFile`. El método `GetPropertyValue` toma como entrada criterios de búsqueda y devuelve las líneas de un archivo de texto que coinciden con los criterios de búsqueda. Los métodos dinámicos proporcionados por la clase `ReadOnlyFile` llaman al método `GetPropertyValue` para recuperar los resultados correspondientes.  
  
    [!code-csharp[VbDynamicWalkthrough#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#5)]
    [!code-vb[VbDynamicWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#5)]  
  
10. Después del método `GetPropertyValue`, agregue el código siguiente para invalidar el método <xref:System.Dynamic.DynamicObject.TryGetMember%2A> de la clase <xref:System.Dynamic.DynamicObject>. Se llama al método <xref:System.Dynamic.DynamicObject.TryGetMember%2A> cuando se solicita un miembro de una clase dinámica y no se especifican argumentos. El argumento `binder` contiene información sobre el miembro al que se hace referencia y el argumento `result` hace referencia al resultado devuelto para el miembro especificado. El método <xref:System.Dynamic.DynamicObject.TryGetMember%2A> devuelve un valor booleano que devuelve `true` si el miembro solicitado existe. En caso contrario, devuelve `false`.  
  
    [!code-csharp[VbDynamicWalkthrough#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#6)]
    [!code-vb[VbDynamicWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#6)]
  
11. Después del método `TryGetMember`, agregue el código siguiente para invalidar el método <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> de la clase <xref:System.Dynamic.DynamicObject>. Se llama al método <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> cuando se solicita un miembro de una clase dinámica con argumentos. El argumento `binder` contiene información sobre el miembro al que se hace referencia y el argumento `result` hace referencia al resultado devuelto para el miembro especificado. El argumento `args` contiene una matriz de los argumentos que se pasan al miembro. El método <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> devuelve un valor booleano que devuelve `true` si el miembro solicitado existe. En caso contrario, devuelve `false`.  
  
    La versión personalizada del método `TryInvokeMember` espera que el primer argumento sea un valor del enumerador `StringSearchOption` que se ha definido en un paso anterior. El método `TryInvokeMember` espera que el segundo argumento sea un valor booleano. Si uno o ambos argumentos son valores válidos, se pasan al método `GetPropertyValue` para recuperar los resultados.  
  
    [!code-csharp[VbDynamicWalkthrough#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#7)]
    [!code-vb[VbDynamicWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#7)]
  
12. Guarde y cierre el archivo.  
  
#### <a name="to-create-a-sample-text-file"></a>Para crear un archivo de texto de ejemplo  
  
1. Haga clic con el botón derecho en el proyecto DynamicSample, seleccione **Agregar** y, después, haga clic en **Nuevo elemento**. En el panel **Plantillas instaladas** seleccione **General** y, luego, la plantilla **Archivo de texto**. Deje el nombre predeterminado TextFile1.txt en el cuadro **Nombre** y haga clic en **Agregar**. Se agregará un archivo de texto nuevo al proyecto.  
  
2. Copie el texto siguiente en el archivo TextFile1.txt.  
  
    ```text  
    List of customers and suppliers  
  
    Supplier: Lucerne Publishing (https://www.lucernepublishing.com/)  
    Customer: Preston, Chris  
    Customer: Hines, Patrick  
    Customer: Cameron, Maria  
    Supplier: Graphic Design Institute (https://www.graphicdesigninstitute.com/)
    Supplier: Fabrikam, Inc. (https://www.fabrikam.com/)
    Customer: Seubert, Roxanne  
    Supplier: Proseware, Inc. (http://www.proseware.com/)
    Customer: Adolphi, Stephan  
    Customer: Koch, Paul  
    ```  
  
3. Guarde y cierre el archivo.  
  
#### <a name="to-create-a-sample-application-that-uses-the-custom-dynamic-object"></a>Para crear una aplicación de ejemplo que usa el objeto dinámico personalizado  
  
1. En el **Explorador de soluciones**, haga doble clic en el archivo Module1.vb si usa Visual Basic o en el archivo Program.cs si usa Visual C#.  
  
2. Agregue el código siguiente al procedimiento Main para crear una instancia de la clase `ReadOnlyFile` para el archivo TextFile1.txt. El código usa el enlace en tiempo de ejecución para llamar a miembros dinámicos y recuperar líneas de texto que contienen la cadena "Customer".  
  
     [!code-csharp[VbDynamicWalkthrough#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/program.cs#8)]
     [!code-vb[VbDynamicWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/module1.vb#8)]
  
3. Guarde el archivo y presione CTRL+F5 para compilar y ejecutar la aplicación.  
  
## <a name="calling-a-dynamic-language-library"></a>Llamar a una biblioteca de lenguaje dinámico  

El siguiente proyecto que cree en este tutorial tendrá acceso a una biblioteca escrita en el lenguaje dinámico IronPython.
  
### <a name="to-create-a-custom-dynamic-class"></a>Para crear una clase dinámica personalizada
  
1. En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.  
  
2. En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**. Seleccione **Aplicación de consola** en el panel **Plantillas**. En el cuadro **Nombre**, escriba `DynamicIronPythonSample` y haga clic en **Aceptar**. Se crea el proyecto.  
  
3. Si usa Visual Basic, haga clic con el botón derecho en el proyecto DynamicIronPythonSample y luego haga clic en **Propiedades**. Haga clic en la pestaña **Referencias**. Haga clic en el botón **Agregar**. Si usa Visual C#, en el **Explorador de soluciones**, haga clic con el botón derecho en la carpeta **Referencias** y, después, haga clic en **Agregar referencia**.  
  
4. En la pestaña **Examinar**, vaya a la carpeta donde están instaladas las bibliotecas de IronPython. Por ejemplo, C:\Program Files\IronPython 2.6 para .NET 4.0. Seleccione las bibliotecas **IronPython.dll**, **IronPython.Modules.dll**, **Microsoft.Scripting.dll** y **Microsoft.Dynamic.dll**. Haga clic en **Aceptar**.  
  
5. Si usa Visual Basic, edite el archivo Module1.vb. Si usa Visual C#, edite el archivo Program.cs.  
  
6. En la parte superior del archivo, agregue el código siguiente para importar los espacios de nombres `Microsoft.Scripting.Hosting` y `IronPython.Hosting` de las bibliotecas de IronPython.  
  
    [!code-csharp[VbDynamicWalkthroughIronPython#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/cs/program.cs#1)]
    [!code-vb[VbDynamicWalkthroughIronPython#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/vb/module1.vb#1)]
  
7. En el método Main, agregue el código siguiente para crear un objeto `Microsoft.Scripting.Hosting.ScriptRuntime` que hospede las bibliotecas de IronPython. El objeto `ScriptRuntime` carga el módulo de biblioteca de IronPython random.py.  
  
     [!code-csharp[VbDynamicWalkthroughIronPython#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/cs/program.cs#2)]
     [!code-vb[VbDynamicWalkthroughIronPython#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/vb/module1.vb#2)]
  
8. Una vez que el código haya cargado el módulo random.py, agregue el código siguiente para crear una matriz de enteros. La matriz se pasa al método `shuffle` del módulo random.py, que ordena aleatoriamente los valores de la matriz.  
  
     [!code-csharp[VbDynamicWalkthroughIronPython#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/cs/program.cs#3)]
     [!code-vb[VbDynamicWalkthroughIronPython#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/vb/module1.vb#3)]
  
9. Guarde el archivo y presione CTRL+F5 para compilar y ejecutar la aplicación.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Dynamic?displayProperty=nameWithType>
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>
- [Uso de tipo dinámico](./using-type-dynamic.md)
- [Enlace en tiempo de compilación y en tiempo de ejecución](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [dynamic](../../language-reference/builtin-types/reference-types.md)
- [Implementar interfaces dinámicas (PDF descargable de Microsoft TechNet)](https://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/implementing-dynamic-interfaces.pdf)
