---
title: 'Tutorial: Inserción de tipos de ensamblados administrados en Visual Studio'
ms.date: 08/19/2019
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
dev_langs:
- csharp
- vb
ms.openlocfilehash: f11fbedad766753ee462c5f597b823493cdaf7cf
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338555"
---
# <a name="walkthrough-embed-types-from-managed-assemblies-in-visual-studio"></a>Tutorial: Inserción de tipos de ensamblados administrados en Visual Studio

Si inserta información de tipos de un ensamblado administrado con nombre seguro, puede acoplar tipos holgadamente en una aplicación para lograr independencia de versiones. Es decir, el programa puede escribirse de modo que use tipos de cualquier versión de una biblioteca administrada sin tener que volver a compilarse para cada nueva versión.

La inserción de tipos se usa a menudo con interoperabilidad COM, como, por ejemplo, una aplicación que use objetos de automatización de Microsoft Office. La inserción de información de tipos permite que la misma versión de un programa funcione con distintas versiones de Microsoft Office en equipos diferentes. No obstante, la inserción de tipos también se puede usar con soluciones totalmente administradas.

Después de especificar las interfaces públicas que se pueden insertar, puede crear clases de tiempo de ejecución que implementen esas interfaces. Un programa cliente puede incrustar la información de tipo de las interfaces en tiempo de diseño haciendo referencia al ensamblado que contiene la configuración y las interfaces públicas de la propiedad `Embed Interop Types` de la referencia a `True`. A continuación, el programa cliente puede cargar instancias de los objetos de tiempo de ejecución escritos como esas interfaces. Esto equivale a usar el compilador de línea de comandos y hacer referencia al ensamblado mediante la [opción -link del compilador](../../csharp/language-reference/compiler-options/link-compiler-option.md).

Si crea otra versión del ensamblado de tiempo de ejecución con nombre seguro, el programa cliente no tiene que volver a compilarse. El programa cliente sigue usando cualquier versión del ensamblado de tiempo de ejecución que encuentre disponible y usa la información de tipo insertada para las interfaces públicas.

En este tutorial, hará lo siguiente:

1. Crear un ensamblado con nombre seguro que tenga una interfaz pública e incluya información de tipo que se puede insertar.
1. Crear un ensamblado de tiempo de ejecución con nombre seguro que implemente la interfaz pública.
1. Crear un programa cliente que inserte la información de tipo de la interfaz pública y cree una instancia de la clase del ensamblado en tiempo de ejecución.
1. Modificar y recompilar el ensamblado en tiempo de ejecución.
1. Ejecute el programa cliente para ver que usa la nueva versión del ensamblado de tiempo de ejecución sin tener que volver a compilarlo.

[!INCLUDE[note_settings_general](../../../includes/note-settings-general-md.md)]

## <a name="conditions-and-limitations"></a>Condiciones y limitaciones

Puede insertar información de tipos desde un ensamblado si se dan las siguientes condiciones:

- El ensamblado expone al menos una interfaz pública.
- Las interfaces insertadas se anotan con atributos `ComImport` y atributos `Guid` con GUID únicos.
- El ensamblado se anota con los atributos `ImportedFromTypeLib` o `PrimaryInteropAssembly` y un atributo `Guid` de nivel de ensamblado. Las plantillas de proyecto de Visual C# y Visual Basic incluyen un atributo `Guid` de nivel de ensamblado de forma predeterminada.

Dado que la función principal de la inserción de tipos es admitir ensamblados de interoperabilidad COM, cuando se inserta información de tipos en una solución totalmente administrada, se aplican las siguientes limitaciones:

- Solo se insertan los atributos específicos de interoperabilidad COM. El resto de atributos se omiten.
- Si un tipo usa parámetros genéricos y el tipo del parámetro genérico es insertado, ese tipo no se puede usar más allá de un límite de ensamblado. Entre los ejemplos de cruce de un límite de ensamblado se incluyen llamar a un método desde otro ensamblado o derivar un tipo desde un tipo definido en otro ensamblado.
- Las constantes no se insertan.
- La clase <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> no admite un tipo insertado como clave. Puede implementar su propio tipo de diccionario que admita un tipo insertado como clave.

## <a name="create-an-interface"></a>Creación de una interfaz

El primer paso es crear el ensamblado de la interfaz de equivalencia de tipos.

1. En Visual Studio, seleccione **Archivo** > **Nuevo** > **Proyecto**.

1. En el cuadro de diálogo **Crear un nuevo proyecto**, escriba *biblioteca de clases* en el cuadro **Buscar plantillas**. Seleccione la plantilla **Biblioteca de clases (.NET Framework)** de C# o Visual Basic de la lista y, luego, seleccione **Siguiente**.

1. En el cuadro de diálogo **Configure su nuevo proyecto**, en **Nombre del proyecto**, escriba *TypeEquivalenceInterface* y, a continuación, seleccione **Crear**. Se crea el proyecto.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *Class1.cs* o en *Class1.vb*, seleccione **Cambiar nombre** y cambie el nombre del archivo de *Class1* a *ISampleInterface*. Responda **Sí** al aviso para cambiar también el nombre de la clase a `ISampleInterface`. Esta clase representa la interfaz pública de la clase.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceInterface** y, a continuación, seleccione **Propiedades**.

1. Seleccione **Compilar** en el panel izquierdo de la pantalla **Propiedades** y establezca la **Ruta de acceso de salida** en una ubicación del equipo, como *C:\TypeEquivalenceSample* . En este tutorial se utiliza la misma ubicación.

1. Seleccione **Firmar** en el panel izquierdo de la pantalla **Propiedades** y, a continuación, active la casilla **Firmar el ensamblado**. En la lista desplegable de **Elija un archivo de clave de nombre seguro**, seleccione **Nuevo**.

1. En el cuadro de diálogo **Crear clave de nombre seguro**, en **Nombre de archivo de clave**, escriba *key.snk*. Desactive la casilla **Proteger mi archivo de clave mediante contraseña** y, a continuación, seleccione **Aceptar**.

1. Abra el archivo de clase *ISampleInterface* en el editor de código y reemplace su contenido por el código siguiente para crear la interfaz `ISampleInterface`:

   ```csharp
   using System;
   using System.Runtime.InteropServices;

   namespace TypeEquivalenceInterface
   {
       [ComImport]
       [Guid("8DA56996-A151-4136-B474-32784559F6DF")]
       public interface ISampleInterface
       {
           void GetUserInput();
           string UserInput { get; }
       }
   }
   ```

   ```vb
   Imports System.Runtime.InteropServices

   <ComImport()>
   <Guid("8DA56996-A151-4136-B474-32784559F6DF")>
   Public Interface ISampleInterface
       Sub GetUserInput()
       ReadOnly Property UserInput As String
   End Interface
   ```

1. En el menú **Herramientas**, seleccione **Crear GUID** y, en el cuadro de diálogo **Crear GUID**, seleccione **Formato de registro**. Seleccione **Copiar** y, a continuación, **Salir**.

1. En el atributo `Guid` del código, reemplace el GUID de ejemplo por el GUID que ha copiado y elimine las llaves ( **{ }** ).

1. En el **Explorador de soluciones**, expanda la carpeta **Propiedades** y seleccione el archivo *AssemblyInfo.cs* o el archivo *AssemblyInfo.vb*. En el editor de código, agregue el siguiente atributo al archivo:

   ```csharp
   [assembly: ImportedFromTypeLib("")]
   ```

   ```vb
   <Assembly: ImportedFromTypeLib("")>
   ```

1. Seleccione **Archivo** > **Guardar todo** o presione **Ctrl**+**Mayús**+**S** para guardar los archivos y el proyecto.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceInterface** y seleccione **Compilar**. El archivo DLL de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada, por ejemplo, *C:\TypeEquivalenceSample*.

## <a name="create-a-runtime-class"></a>Creación de una clase en tiempo de ejecución

A continuación, cree la clase en tiempo de ejecución de equivalencia de tipos.

1. En Visual Studio, seleccione **Archivo** > **Nuevo** > **Proyecto**.

1. En el cuadro de diálogo **Crear un nuevo proyecto**, escriba *biblioteca de clases* en el cuadro **Buscar plantillas**. Seleccione la plantilla **Biblioteca de clases (.NET Framework)** de C# o Visual Basic de la lista y, luego, seleccione **Siguiente**.

1. En el cuadro de diálogo **Configure su nuevo proyecto**, en **Nombre del proyecto**, escriba *TypeEquivalenceRuntime* y, a continuación, seleccione **Crear**. Se crea el proyecto.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *Class1.cs* o en *Class1.vb*, seleccione **Cambiar nombre** y cambie el nombre del archivo de *Class1* a *SampleClass*. Responda **Sí** al aviso para cambiar también el nombre de la clase a `SampleClass`. Esta clase implementa la interfaz `ISampleInterface` .

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceInterface** y seleccione **Propiedades**.

1. Seleccione **Compilar** en el panel izquierdo de la pantalla **Propiedades** y establezca la **Ruta de acceso de salida** en la misma ubicación que usó para el proyecto TypeEquivalenceInterface, por ejemplo, *C:\TypeEquivalenceSample*.

1. Seleccione **Firmar** en el panel izquierdo de la pantalla **Propiedades** y, a continuación, active la casilla **Firmar el ensamblado**. En la lista desplegable de **Elija un archivo de clave de nombre seguro**, seleccione **Nuevo**.

1. En el cuadro de diálogo **Crear clave de nombre seguro**, en **Nombre de archivo de clave**, escriba *key.snk*. Desactive la casilla **Proteger mi archivo de clave mediante contraseña** y, a continuación, seleccione **Aceptar**.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceRuntime** y seleccione **Agregar** > **referencia**.

1. En el cuadro de diálogo **Administrador de referencias**, seleccione **Examinar** y vaya a la ruta de acceso de la carpeta de salida. Seleccione el archivo *TypeEquivalenceInterface.dll*, seleccione **Agregar** y, a continuación, haga clic en **Aceptar**.

1. En el **Explorador de soluciones**, expanda la carpeta **Referencias** y seleccione la referencia **TypeEquivalenceInterface**. En el panel **Propiedades**, establezca **Versión específica** en **False** si aún no lo está.

1. Abra el archivo de clase *SampleClass* en el editor de código y reemplace su contenido por el código siguiente para crear la clase `SampleClass`:

   ```csharp
   using System;
   using TypeEquivalenceInterface;

   namespace TypeEquivalenceRuntime
   {
       public class SampleClass : ISampleInterface
       {
           private string p_UserInput;
           public string UserInput { get { return p_UserInput; } }

           public void GetUserInput()
           {
               Console.WriteLine("Please enter a value:");
               p_UserInput = Console.ReadLine();
           }
       }
   }
   ```

   ```vb
   Imports TypeEquivalenceInterface

   Public Class SampleClass
       Implements ISampleInterface

       Private p_UserInput As String
       Public ReadOnly Property UserInput() As String Implements ISampleInterface.UserInput
           Get
               Return p_UserInput
           End Get
       End Property

       Public Sub GetUserInput() Implements ISampleInterface.GetUserInput
           Console.WriteLine("Please enter a value:")
           p_UserInput = Console.ReadLine()
       End Sub
   End Class
   ```

1. Seleccione **Archivo** > **Guardar todo** o presione **Ctrl**+**Mayús**+**S** para guardar los archivos y el proyecto.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceRuntime** y seleccione **Compilar**. El archivo DLL de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada.

## <a name="create-a-client-project"></a>Creación de un proyecto de cliente

Por último, cree un programa cliente de equivalencia de tipos que haga referencia al ensamblado de la interfaz.

1. En Visual Studio, seleccione **Archivo** > **Nuevo** > **Proyecto**.

1. En el cuadro de diálogo **Crear un nuevo proyecto**, escriba *consola* en el cuadro **Buscar plantillas**. Seleccione la plantilla **Aplicación de consola (.NET Framework)** de C# o Visual Basic de la lista y, a continuación, seleccione **Siguiente**.

1. En el cuadro de diálogo **Configure su nuevo proyecto**, en **Nombre del proyecto**, escriba *TypeEquivalenceClient* y, a continuación, seleccione **Crear**. Se crea el proyecto.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceClient** y seleccione **Propiedades**.

1. Seleccione **Compilar** en el panel izquierdo de la pantalla **Propiedades** y establezca la **Ruta de acceso de salida** en la misma ubicación que usó para el proyecto TypeEquivalenceInterface, por ejemplo, *C:\TypeEquivalenceSample*.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceClient** y seleccione **Agregar** > **referencia**.

1. En el cuadro de diálogo **Administrador de referencias**, si el archivo **TypeEquivalenceInterface.dll** ya aparece en la lista, selecciónelo. Si no es así, seleccione **Examinar**, vaya a la carpeta de la ruta de acceso de salida, seleccione el archivo *TypeEquivalenceInterface.dll* (no *TypeEquivalenceRuntime.dll*) y, después, seleccione **Agregar**. Seleccione **Aceptar**.

1. En el **Explorador de soluciones**, expanda la carpeta **Referencias** y seleccione la referencia **TypeEquivalenceInterface**. En el panel **Propiedades**, establezca **Incrustar tipos de interoperabilidad** en **True**.

1. Abra el archivo *Program.cs* o el archivo *Module1.vb* en el editor de código y reemplace su contenido por el código siguiente para crear el programa cliente:

   ```csharp
   using System;
   using System.Reflection;
   using TypeEquivalenceInterface;

   namespace TypeEquivalenceClient
   {
       class Program
       {
           static void Main(string[] args)
           {
               Assembly sampleAssembly = Assembly.Load("TypeEquivalenceRuntime");
               ISampleInterface sampleClass =
                   (ISampleInterface)sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass");
               sampleClass.GetUserInput();
               Console.WriteLine(sampleClass.UserInput);
               Console.WriteLine(sampleAssembly.GetName().Version.ToString());
               Console.ReadLine();
           }
       }
   }
   ```

   ```vb
   Imports System.Reflection
   Imports TypeEquivalenceInterface

   Module Module1

       Sub Main()
           Dim sampleAssembly = Assembly.Load("TypeEquivalenceRuntime")
           Dim sampleClass As ISampleInterface = CType( _
               sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass"), ISampleInterface)
           sampleClass.GetUserInput()
           Console.WriteLine(sampleClass.UserInput)
           Console.WriteLine(sampleAssembly.GetName().Version)
           Console.ReadLine()
       End Sub

   End Module
   ```

1. Seleccione **Archivo** > **Guardar todo** o presione **Ctrl**+**Mayús**+**S** para guardar los archivos y el proyecto.

1. Presione **Ctrl**+**F5** para compilar y ejecutar el programa. Tenga en cuenta que la salida de la consola devuelve la versión de ensamblado **1.0.0.0**.

## <a name="modify-the-interface"></a>Modificación de la interfaz

Ahora, modifique el ensamblado de la interfaz y cambie su versión.

1. En Visual Studio, seleccione **Archivo** > **Abrir** > **Proyecto o solución** y abra el proyecto **TypeEquivalenceInterface**.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceInterface** y seleccione **Propiedades**.

1. Seleccione **Aplicación** en el panel izquierdo de la pantalla **Propiedades** y, a continuación, seleccione **Información de ensamblado**.

1. En el cuadro de diálogo **Información de ensamblado**, cambie los valores de **Versión del ensamblado** y **Versión del archivo** a *2.0.0.0* y, a continuación, seleccione **Aceptar**.

1. Abra el archivo *SampleInterface.cs* o *SampleInterface.vb* y agregue la siguiente línea de código a la interfaz `ISampleInterface`:

   ```csharp
   DateTime GetDate();
   ```

   ```vb
   Function GetDate() As Date
   ```

1. Seleccione **Archivo** > **Guardar todo** o presione **Ctrl**+**Mayús**+**S** para guardar los archivos y el proyecto.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceInterface** y seleccione **Compilar**. Se compila una nueva versión del archivo DLL de biblioteca de clases y se guarda en la ruta de acceso de salida de la compilación.

## <a name="modify-the-runtime-class"></a>Modificación de la clase en tiempo de ejecución

Modifique también la clase en tiempo de ejecución y actualice su versión.

1. En Visual Studio, seleccione **Archivo** > **Abrir** > **Proyecto o solución** y abra el proyecto **TypeEquivalenceRuntime**.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceRuntime** y seleccione **Propiedades**.

1. Seleccione **Aplicación** en el panel izquierdo de la pantalla **Propiedades** y, a continuación, seleccione **Información de ensamblado**.

1. En el cuadro de diálogo **Información de ensamblado**, cambie los valores de **Versión del ensamblado** y **Versión del archivo** a *2.0.0.0* y, a continuación, seleccione **Aceptar**.

1. Abra el archivo *SampleClass.cs* o el archivo *SampleClass.vb* y agregue el código siguiente a la clase `SampleClass`:

   ```csharp
    public DateTime GetDate()
    {
        return DateTime.Now;
    }
   ```

   ```vb
   Public Function GetDate() As DateTime Implements ISampleInterface.GetDate
       Return Now
   End Function
   ```

1. Seleccione **Archivo** > **Guardar todo** o presione **Ctrl**+**Mayús**+**S** para guardar los archivos y el proyecto.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceRuntime** y seleccione **Compilar**. Se compila una nueva versión del archivo DLL de biblioteca de clases y se guarda en la ruta de acceso de salida de la compilación.

## <a name="run-the-updated-client-program"></a>Ejecución del programa cliente actualizado

Vaya a la ubicación de la carpeta de resultados de compilación y ejecute *TypeEquivalenceClient.exe*. Tenga en cuenta que la salida de la consola ahora refleja la nueva versión del ensamblado `TypeEquivalenceRuntime`, *2.0.0.0*, sin que el programa se vuelva a compilar.

## <a name="see-also"></a>Vea también

- [-link (Opciones del compilador de C#)](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md)
- [Guía de programación de C#](../../csharp/programming-guide/index.md)
- [Conceptos de programación (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
- [Ensamblados de .NET](index.md)
