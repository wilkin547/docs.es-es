---
title: Controlar y generar excepciones en .NET
description: Aprender a usar excepciones en .NET
keywords: .NET, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: bf116df6-0042-46bf-be13-b69864816210
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 7c9ccd455bf0d14122c0547177cc29ace6ebde42
ms.lasthandoff: 02/17/2017

---

# <a name="handling-and-throwing-exceptions-in-net"></a>Controlar y generar excepciones en .NET

Las aplicaciones tienen que ser capaces de controlar de forma coherente los errores que se producen durante la ejecución. .NET proporciona un modelo para notificar errores a las aplicaciones de manera uniforme: las operaciones .NET indican errores iniciando excepciones.

## <a name="exceptions"></a>Excepciones

Una excepción es cualquier condición de error o comportamiento inesperado que encuentra un programa en ejecución. Las excepciones pueden iniciarse debido a un error en el código propio o en el código al que se llama (por ejemplo, una biblioteca compartida), a recursos del sistema operativo no disponibles, a condiciones inesperadas que encuentra el runtime (por ejemplo, imposibilidad de comprobar el código), etc. La aplicación puede recuperarse de algunas de estas condiciones, pero no de todas. Aunque es posible recuperarse de la mayoría de las excepciones que se producen en la aplicación, no ocurre lo mismo con las excepciones de runtime.

En .NET, una excepción es un objeto que hereda de la clase [System.Exception](xref:System.Exception). Una excepción se inicia desde un área del código en la que ha producido un problema. La excepción se pasa hacia arriba en la pila hasta que la aplicación la controla o el programa finaliza.

## <a name="exceptions-vs-traditional-error-handling-methods"></a>Comparación entre los métodos tradicionales de control de errores y las excepciones

Tradicionalmente, el modelo de control de errores de un lenguaje se basaba en el modo exclusivo del lenguaje de detectar los errores y buscarles controladores, o bien en el mecanismo de control de errores ofrecido por el sistema operativo. La forma en que .NET implementa el control de excepciones proporciona las siguientes ventajas:

- La administración e iniciación de excepciones funciona de igual modo para los lenguajes de programación. NET.

- No requiere ninguna sintaxis de lenguaje específica para controlar las excepciones, pero permite que cada lenguaje defina su propia sintaxis.

- Las excepciones pueden iniciarse en varios procesos en incluso límites de máquina.

- Se puede agregar el código de control de excepciones a una aplicación para aumentar la confiabilidad del programa.

Las excepciones ofrecen ventajas sobre otros métodos de notificación de errores, por ejemplo, los códigos de retorno. Lo errores no pasan desapercibidos porque si se inicia una excepción y no la controla, el runtime finaliza la aplicación. Los valores no válidos no continúan propagándose por el sistema como resultado de que el código no pueda encontrar un código de retorno de error. 

## <a name="exception-class-and-properties"></a>Clase Exception y propiedades

La clase @System.Exception es la clase base de la que heredan las excepciones. Por ejemplo, la jerarquía de clases de @System.InvalidCastException es como sigue:

```
Object
  Exception
    SystemException
       InvalidCastException
```

La clase @System.Exception tiene las siguientes propiedades que facilitan la comprensión de una excepción.

| Nombre de la propiedad | Descripción |
| ------------- | ----------- |
| @System.Exception.Data | Un @System.Collections.IDictionary que contiene datos arbitrarios en pares de clave y valor. |
| @System.Exception.HelpLink | Puede contener una dirección URL (o URN) a un archivo de ayuda que proporciona amplia información sobre la causa de una excepción. |
| @System.Exception.InnerException | Esta propiedad puede usarse para crear y mantener una serie de excepciones durante el control de excepciones. Puede usarla para crear una nueva excepción que contiene excepciones detectadas con anterioridad. La segunda excepción en la propiedad @System.Exception.InnerException puede capturar la excepción original, lo que permite que el código que controla la segunda excepción examine la información adicional. Por ejemplo, supongamos que tiene un método que recibe un argumento que contiene un formato incorrecto.  El código intenta leer el argumento, pero se inicia una excepción. El método detecta la excepción e inicia @System.FormatException. Para mejorar la capacidad del autor de llamada a la hora de determinar por qué se inicia una excepción, a veces, para un método es recomendable detectar una excepción iniciada por una rutina auxiliar y, después, iniciar una excepción más indicativa del error que se ha producido. Puede crear una excepción nueva y más significativa, donde se puede establecer la referencia a la excepción interna en la excepción original. Después, se puede iniciar esta excepción más significativa para el autor de llamada. Tenga en cuenta que con esta funcionalidad, puede crear una serie de excepciones vinculadas que termina con la excepción que se inicia en primer lugar. |
| @System.Exception.Message | Proporciona detalles sobre la causa de una excepción.
| @System.Exception.Source | Devuelve o establece el nombre de la aplicación o del objeto que generó el error. |
| @System.Exception.StackTrace | Contiene un seguimiento de la pila que puede usarse para determinar dónde se produjo un error. El seguimiento de la pila contiene el nombre del archivo de código fuente y el número de línea del programa si está disponible la información de depuración. |

La mayoría de las clases que heredan de @System.Exception no implementan miembros adicionales ni proporcionan funciones adicionales; simplemente heredan de @System.Exception. Por tanto, se puede encontrar la información más importante para una excepción en la jerarquía de clases de excepción, el nombre de la excepción y la información contenida en la excepción.

Se recomienda iniciar y detectar solo los objetos que se derivan de @System.Exception,, pero puede iniciar cualquier objeto que se deriva de la clase @System.Object como una excepción. Tenga en cuenta que no todos los lenguajes admiten iniciar y detectar objetos que no se derivan de @System.Exception.

## <a name="common-exceptions"></a>Excepciones comunes

En la tabla siguiente se muestra algunas excepciones comunes con ejemplos de las causas que las originan.

| Tipo de excepción | Tipo base | Descripción | Ejemplo |
| -------------- | --------- | ----------- | ------- |
| @System.Exception | @System.Object | Clase base de todas las excepciones. | Ninguno (utilice una clase derivada de esta excepción). |
| @System.IndexOutOfRangeException | @System.Exception | El tiempo de ejecución la genera solo cuando una matriz no está correctamente indexada. | La indexación de una matriz fuera de su intervalo válido: `arr[arr.Length+1]` |
| @System.NullReferenceException | @System.Exception | El tiempo de ejecución la genera solo cuando se hace referencia a un objeto null. | `object o = null; o.ToString();` |
| @System.InvalidOperationException | @System.Exception | Los métodos la generan si se produce un estado no válido. | Llamada a `Enumerator.GetNext()` después de quitar un elemento de la colección subyacente. |
| @System.ArgumentException | @System.Exception | Clase base de todas las excepciones de argumento. | Ninguno (utilice una clase derivada de esta excepción). |
| @System.ArgumentNullException | @System.Exception | Los métodos que no permiten que un argumento sea null la generan. | `String s = null; "Calculate".IndexOf (s);` |
| @System.ArgumentOutOfRangeException | @System.Exception | Los métodos que comprueban que los argumentos se encuentran en un intervalo determinado la generan. | `String s = "string"; s.Substring(s.Length+1);` |

## <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a>Cómo usar el bloque Try/Catch para detectar excepciones

Coloque las secciones del código que pueden iniciar excepciones en un bloque `try` y coloque el código que controla las excepciones en un bloque `catch`. El bloque `catch` es una serie de instrucciones que comienzan con la palabra clave `catch`, seguido de un tipo de excepción y la acción que se debe realizar.

El siguiente ejemplo de código usa un bloque `try`/`catch` para detectar una posible excepción. El método `Main` contiene un bloque `try` con una instrucción de @System.IO.StreamReader que abre un archivo de datos denominado `data.txt` y escribe una cadena del archivo. Después del bloque `try` aparece un bloque `catch` que detecta cualquier excepción que se produzca desde el bloque `try`.

C#
```
using System;
using System.IO;

public class ProcessFile
{
    public static void Main()
    {
        try
        {
            StreamReader sr = File.OpenText("data.txt");
            Console.WriteLine("The first line of this file is {0}", sr.ReadLine());
            sr.Dispose();
        }
        catch (Exception e)
        {
            Console.WriteLine("An error occurred: '{0}'", e);
        }
    }
}
```

Common Language Runtime detecta las excepciones que no se detectan mediante un bloque Catch. Dependiendo de cómo esté configurado el runtime, aparece un cuadro de diálogo de depuración, el programa deja de ejecutarse y aparece un cuadro de diálogo con información sobre la excepción o bien se imprime un error en STDERR.

> [!NOTE] 
> Prácticamente cualquier línea de código puede originar una excepción, especialmente las excepciones iniciadas por Common Language Runtime, como @System.OutOfMemoryException. La mayoría de las aplicaciones no tienen que tratar con estas excepciones, pero debe tener en cuenta esta posibilidad al escribir bibliotecas que puedan usar otros usuarios. Para obtener sugerencias sobre cuándo establecer el código en un bloque Try, consulte [Procedimientos recomendados para excepciones](#best-practices-for-exceptions).
 
## <a name="how-to-use-specific-exceptions-in-a-catch-block"></a>Cómo usar excepciones específicas en un bloque Catch

El ejemplo de código anterior muestra una instrucción `catch` básica que detecta cualquier excepción. Pero en general, en programación es recomendable detectar un tipo de excepción específico en lugar de usar una instrucción `catch` básica.

Cuando se produce una excepción, se pasa a la pila y cada bloque Catch tiene la oportunidad de controlarla. El orden de las instrucciones Catch es importante. Ponga los bloques Catch dirigidos a excepciones específicas antes de un bloque Catch de excepción general o el compilador podría emitir un error. El bloque Catch adecuado se determina haciendo coincidir el tipo de la excepción con el nombre de la excepción especificada en el bloque Catch. Si no hay ningún bloque Catch específico, la excepción se detecta mediante un bloque Catch general, si existe alguno.

En el siguiente ejemplo de código se usa un bloque `try`/`catch` para detectar una @System.InvalidCastException. El ejemplo crea una clase denominada `Employee` con una propiedad única, el nivel de empleado (`Emlevel`). Un método, `PromoteEmployee`, toma un objeto e incrementa el nivel del empleado. Una @System.InvalidCastException se produce cuando una instancia de @System.DateTime se pasa al método `PromoteEmployee`.

C#
```
using System;

public class Employee
{
    //Create employee level property.
    public int Emlevel
    {
        get
        {
            return(emlevel);
        }
        set
        {
            emlevel = value;
        }
    }

    private int emlevel = 0;
}

public class Ex13
{
    public static void PromoteEmployee(Object emp)
    {
        //Cast object to Employee.
        Employee e = (Employee) emp;
        // Increment employee level.
        e.Emlevel = e.Emlevel + 1;
    }

    public static void Main()
    {
        try
        {
            Object o = new Employee();
            DateTime newyears = new DateTime(2001, 1, 1);
            //Promote the new employee.
            PromoteEmployee(o);
            //Promote DateTime; results in InvalidCastException as newyears is not an employee instance.
            PromoteEmployee(newyears);
        }
        catch (InvalidCastException e)
        {
            Console.WriteLine("Error passing data to PromoteEmployee method. " + e.Message);
        }
    }
}
```

## <a name="how-to-use-finally-blocks"></a>Cómo usar bloques Finally

Cuando se produce una excepción, se detiene la ejecución y se proporciona el control al controlador de excepciones adecuado. A menudo, esto significa que se omiten líneas de código que esperaba que se ejecuten. Se debe realizar alguna limpieza de recursos, como cerrar un archivo, aunque se inicie una excepción. Para ello, puede usar un bloque `finally`. Un bloque `finally` siempre se ejecuta, independientemente de si se inicia una excepción.

En el siguiente ejemplo de código se usa un bloque `try`/`catch` para detectar una @System.ArgumentOutOfRangeException. El método `Main` crea dos matrices e intenta copiar una en la otra. La acción genera un @System.ArgumentOutOfRangeException y el error se escribe en la consola. Este bloque `finally` se ejecuta independientemente del resultado de la acción de copia.

C#
```
using System;

class ArgumentOutOfRangeExample
{
    public static void Main()
    {
        int[] array1 = {0, 0};
        int[] array2 = {0, 0};

        try
        {
            Array.Copy(array1, array2, -1);
        }
        catch (ArgumentOutOfRangeException e)
        {
            Console.WriteLine("Error: {0}", e);
        }
        finally
        {
            Console.WriteLine("This statement is always executed.");
        }
    }
}
```

## <a name="how-to-explicitly-throw-exceptions"></a>Cómo iniciar excepciones explícitamente

Puede iniciar explícitamente una excepción mediante la instrucción `throw`. También se puede iniciar una excepción detectada usando de nuevo la instrucción `throw`. En diseño de código, es recomendable agregar información a una excepción que se vuelve a iniciar para proporcionar más información durante la depuración.

En el siguiente ejemplo de código se usa un bloque `try`/`catch` para detectar una posible @System.IO.FileNotFoundException. Seguido del bloque `try` va un bloque `catch` que detecta @System.IO.FileNotFoundException y escribe un mensaje a la consola si no se encuentra el archivo de datos. La siguiente instrucción es `throw` que inicia un parámetro @System.IO.FileNotFoundException nuevo y agrega información de texto a la excepción.

C#
```
using System;
using System.IO;

public class ProcessFile
{
   public static void Main()
      {
      FileStream fs = null;
      try   
      {
         //Opens a text tile.
         fs = new FileStream(@"C:\temp\data.txt", FileMode.Open);
         StreamReader sr = new StreamReader(fs);
         string line;

         //A value is read from the file and output to the console.
         line = sr.ReadLine();
         Console.WriteLine(line);
      }
      catch(FileNotFoundException e)
      {
         Console.WriteLine("[Data File Missing] {0}", e);
         throw new FileNotFoundException(@"[data.txt not in c:\temp directory]",e);
      }
      finally
      {
         if (fs != null)
            fs.Dispose();
      }
   }
}
```

## <a name="how-to-create-user-defined-exceptions"></a>Cómo crear excepciones definidas por el usuario

.NET proporciona una jerarquía de clases de excepciones derivadas en última instancia de la clase base @System.Exception. Pero si ninguna de las excepciones predefinidas satisface sus necesidades, puede crear sus propias clases de excepciones derivadas de la clase @System.Exception.

Al crear sus propias excepciones, termine el nombre de clase de la excepción definida por el usuario con la palabra "Exception" e implemente los tres constructores comunes, como se muestra en el ejemplo siguiente. En el ejemplo se define una nueva clase de excepción denominada `EmployeeListNotFoundException`. La clase se deriva de @System.Exception e incluye tres constructores.

C#
```
using System;

public class EmployeeListNotFoundException: Exception
{
    public EmployeeListNotFoundException()
    {
    }

    public EmployeeListNotFoundException(string message)
        : base(message)
    {
    }

    public EmployeeListNotFoundException(string message, Exception inner)
        : base(message, inner)
    {
    }
}
```

> [!NOTE]
> En situaciones en que use la comunicación remota, debe asegurarse de que los metadatos de todas las excepciones definidas por el usuario estén disponibles en el servidor (destinatario) y en el cliente (el objeto proxy o autor de la llamada). Para obtener más información, consulte [Procedimientos recomendados para excepciones](#best-practices-for-exceptions).

## <a name="best-practices-for-exceptions"></a>Procedimientos recomendados para excepciones

Una aplicación diseñada correctamente controla las excepciones y los errores para evitar que se bloquee. En este artículo se describen los procedimientos recomendados para controlar y crear excepciones.

### <a name="use-trycatchfinally-blocks"></a>Uso de bloques Try/Catch/Finally

Use bloques de código `try`/`catch`/`finally` que podría generar una excepción. 

Ordene siempre las excepciones de los bloques `catch` de la más específica a la menos.

Use un bloque `finally` para limpiar los recursos, tanto si puede recuperarlos como si no.

### <a name="handle-common-conditions-without-throwing-exceptions"></a>Administrar condiciones comunes sin iniciar excepciones

Para las condiciones con probabilidad de producirse, pero que podrían desencadenar una excepción, considere la posibilidad de controlarlas de forma que se evite la excepción. Por ejemplo, si intenta se cerrar una conexión que ya está cerrada, obtendrá `InvalidOperationException`. Se puede evitar mediante una instrucción `if` para comprobar el estado de conexión antes de intentar cerrarla.

C#
```
if (conn.State != ConnectionState.Closed)
{
    conn.Close();
}
```

Si no comprueba el estado de la conexión antes de cerrar, se puede detectar la excepción `InvalidOperationException`.

C#
```
try
{
    conn.Close();
}
catch (InvalidOperationException ex)
{
    Console.WriteLine(ex.GetType().FullName);
    Console.WriteLine(ex.Message);
}
```

El método que se elija depende de la frecuencia con la que espera que se produzca el evento.

- Utilice el control de excepciones si el evento no se produce con frecuencia, es decir, si el evento es muy excepcional e indica un error (como un final de archivo inesperado). Cuando se usa el control de excepciones, se ejecuta menos código en condiciones normales.

- Compruebe condiciones de error en el código cuando el evento se produce con frecuencia y se puede considerar como parte de la ejecución normal. Cuando se buscan condiciones de error comunes, se ejecuta menos código porque se evitan excepciones.

### <a name="design-classes-so-that-exceptions-can-be-avoided"></a>Diseñar clases para que se puedan evitar excepciones

Una clase puede proporcionar métodos o propiedades que permiten evitar realizar una llamada que desencadenaría una excepción. Por ejemplo, una clase @System.IO.FileStream proporciona métodos que ayudan a determinar si se ha alcanzado el final del archivo. Esto se puede usar para evitar la excepción que se inicia si se lee más allá del final del archivo. En el ejemplo siguiente se muestra cómo leer hasta el final de un archivo sin desencadenar una excepción.

C#
```
class FileRead
{
    public void ReadAll(FileStream fileToRead)
    {
        // This if statement is optional
        // as it is very unlikely that
        // the stream would ever be null.
        if (fileToRead == null)
        {
            throw new System.ArgumentNullException();
        }

        int b;

        // Set the stream position to the beginning of the file.
        fileToRead.Seek(0, SeekOrigin.Begin);

        // Read each byte to the end of the file.
        for (int i = 0; i < fileToRead.Length; i++)
        {
            b = fileToRead.ReadByte();
            Console.Write(b.ToString());
            // Or do something else with the byte.
        }
    }
}
```

Otro modo de evitar excepciones es devolver NULL para los casos de errores muy frecuentes en lugar de iniciar una excepción. Un caso de error muy común se puede considerar como un flujo de control normal. Al devolver un valor null en estos casos, se minimiza el impacto en el rendimiento de una aplicación.

### <a name="throw-exceptions-instead-of-returning-an-error-code"></a>Iniciar excepciones en lugar de devolver un código de error

Las excepciones garantizan que los errores no pasen desapercibidos porque la llamada al código no compruebe un código de retorno. 

### <a name="use-the-predefined-net-exception-types"></a>Uso de los tipos de excepción predefinidos de .NET

Solo se deben introducir nuevas clases de excepción si no se puede aplicar ningún tipo predefinido. Por ejemplo:

- Inicie una excepción @System.InvalidOperationException si un conjunto de propiedades o una llamada a un método no resultan apropiados de acuerdo con el estado actual del objeto.

- Inicie una excepción @System.ArgumentException o una de las clases predefinidas que derivan de @System.ArgumentException si se pasan parámetros no válidos.

### <a name="end-exception-class-names-with-the-word-exception"></a>Termine los nombres de clases de excepción con la palabra `Exception`

Cuando se necesite una excepción personalizada, debe ponerse el nombre apropiado y derivarla de la clase @System.Exception. Por ejemplo:

C#
```
public class MyFileNotFoundException : Exception
{
}
```

### <a name="include-three-constructors-in-custom-exception-classes"></a>Incluir tres constructores en las clases de excepciones personalizadas

Use al menos tres constructores comunes al crear sus propias clases de excepción: el constructor predeterminado, un constructor que tome un mensaje de cadena y un constructor que tome un mensaje de cadena y una excepción interna.

- @System.Exception.%23ctor,, que utiliza valores predeterminados.

- @System.Exception.%23ctor(System.String),, que acepta un mensaje de cadena.

- @System.Exception.%23ctor(System.String,System.Exception),, que acepta un mensaje de cadena y una excepción interna.

Por ejemplo, consulte [Cómo: Crear excepciones definidas por el usuario](#how-to-create-user-defined-exceptions).

### <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a>Asegúrese de que los datos de excepción estén disponibles cuando el código se ejecute de forma remota

Cuando cree excepciones definidas por el usuario, debe garantizar que los metadatos de las excepciones están disponibles para el código que se ejecute de forma remota. 

Por ejemplo, en runtimes de .NET que implementan los dominios de aplicación, pueden producirse excepciones entre dominios de aplicación. Por ejemplo, supongamos que el dominio de aplicación A crea el dominio de aplicación B, que ejecuta código que inicia una excepción. Para que el dominio de aplicación A detecte y controle la excepción correctamente, debe poder encontrar el ensamblado que contiene la excepción iniciada por el dominio de aplicación B. Si el dominio de aplicación B inicia una excepción contenida en un ensamblado en su base de aplicación pero no en la base de aplicación del dominio de aplicación A, el dominio de aplicación A no podrá encontrar la excepción y common language runtime iniciará una excepción de @System.IO.FileNotFoundException. Para evitar esta situación, puede implementar el ensamblado que contiene la información de la excepción de dos maneras:

- Ponga el ensamblado en una base de aplicación compartida por los dos dominios de aplicación.

    \- o -

- Si los dominios no comparten una base de aplicación común, firme el ensamblado que contiene la información de la excepción con un nombre seguro e impleméntelo en la caché global de ensamblados.

### <a name="include-a-localized-description-string-in-every-exception"></a>Incluir una cadena descriptiva localizada en todas las excepciones

El mensaje de error que ve el usuario deriva de la cadena descriptiva de la excepción que se inició y no del nombre de la clase de excepción.

### <a name="use-grammatically-correct-error-messages"></a>Usar mensajes de error gramaticalmente correctos

Escriba frases claras e incluya puntuación final. Cara oración de una cadena descriptiva de una excepción debe acabar con un punto. Por ejemplo, "la tabla del registro se ha desbordado." sería una cadena de descripción adecuada.

### <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a>En excepciones personalizadas, proporcione propiedades adicionales según sea necesario

Únicamente proporcione información adicional para una excepción (además de la cadena descriptiva) si hay un escenario de programación en que dicha información sea útil. Por ejemplo, @System.IO.FileNotFoundException proporciona la propiedad @System.IO.FileNotFoundException.FileName.

### <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a>Colocar instrucciones de iniciación para que el seguimiento de la pila sea útil

El seguimiento de pila comienza en la instrucción en que se produce la excepción y termina en la instrucción `catch` que detecta la excepción.

### <a name="use-exception-builder-methods"></a>Usar métodos de generador de excepciones

Es habitual que una clase produzca la misma excepción desde distintos lugares de su implementación. Para evitar el exceso de código, use métodos auxiliares que creen la excepción y la devuelvan. Por ejemplo:

C#
```
class FileReader
{
    private string fileName;

    public FileReader(string path)
    {
        fileName = path;
    }

    public byte[] Read(int bytes)
    {
        byte[] results = FileUtils.ReadFromFile(fileName, bytes);
        if (results == null)
        {
            throw NewFileIOException();
        }
        return results;
    }

    FileReaderException NewFileIOException()
    {
        string description = "My NewFileIOException Description";

        return new FileReaderException(description);
    }
}

```

En algunos casos, es más apropiado usar el constructor de excepciones para generar la excepción. Un ejemplo es una clase de excepción global, como @System.ArgumentException, 

### <a name="clean-up-intermediate-results-when-throwing-an-exception"></a>Eliminar los resultados intermedios cuando se inicie una excepción

Los autores de llamadas deben poder asumir que no se producen efectos no deseados cuando se produce una excepción desde un método. Por ejemplo, si tiene código que transfiere dinero mediante la retirada de una cuenta y el depósito en otra, y se inicia una excepción mientras se ejecuta el depósito, no quiere que la retirada siga siendo efectiva.

C#
```
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect. 
    to.Deposit(amount);
}
```

Para controlar esta situación se puede detectar cualquier excepción iniciada por la transacción del depósito y revertir la retirada.

C#
```
private static void TransferFunds(Account from, Account to, decimal amount)
{
    string withdrawalTrxID = from.Withdrawal(amount);
    try
    {
        to.Deposit(amount);
    }
    catch
    {
        from.RollbackTransaction(withdrawalTrxID);
        throw
    }
}
```

Este ejemplo muestra el uso de `throw` para volver a iniciar la excepción original, que puede facilitar a los autores de llamada ver la causa del problema real sin tener que examinar la propiedad @System.Exception.InnerException. Como alternativa se puede iniciar una nueva excepción e incluir la excepción original como excepción interna:

C#
```
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new Exception("Withdrawal failed", ex);
}
```

## <a name="see-also"></a>Vea también

Para obtener más información acerca de cómo funcionan las excepciones en. NET, consulte [Qué deben saber los desarrolladores sobre las excepciones en runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md).

