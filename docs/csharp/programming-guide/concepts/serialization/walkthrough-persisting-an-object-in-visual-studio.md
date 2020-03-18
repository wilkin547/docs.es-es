---
title: 'Tutorial: Conservar un objeto con C#'
ms.date: 04/26/2018
ms.openlocfilehash: 85c5d1b711180eda5734d5860d996242c6bc89d1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167575"
---
# <a name="walkthrough-persisting-an-object-using-c"></a>Tutorial: Conservar un objeto con C\#

Puede usar la serialización para conservar los datos de un objeto entre instancias, lo que le permite almacenar valores y recuperarlos la próxima vez que se cree una instancia del objeto.

En este tutorial, creará un objeto `Loan` básico y conservará sus datos en un archivo. Después, recuperará los datos del archivo cuando vuelva a crear el objeto.

> [!IMPORTANT]
> En este ejemplo se crea un nuevo archivo, si este no existe aún. Si una aplicación debe crear un archivo, es necesario que tenga el permiso `Create` en la carpeta. Los permisos se establecen mediante el uso de las listas de control de acceso. Si el archivo ya existe, la aplicación necesitará solo un permiso `Write`, un permiso menor. Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder solo permisos `Read` a un único archivo (en lugar de crear permisos para una carpeta). También es más seguro escribir datos en carpetas de usuario en lugar de hacerlo en la carpeta raíz o en la carpeta Archivos de programa.

> [!IMPORTANT]
> En este ejemplo se almacenan datos en un archivo de formato binario. Estos formatos no deben usarse para datos confidenciales, como contraseñas o información de tarjetas de crédito.

## <a name="prerequisites"></a>Requisitos previos

- Para compilar y ejecutar, instalar el [SDK de .NET Core](https://dotnet.microsoft.com/download).

- Instale el editor de código que prefiera si aún no lo ha hecho.

> [!TIP]
> ¿Es necesario instalar un editor de código? Pruebe [Visual Studio](https://visualstudio.com/downloads).

- El ejemplo requiere C# 7.3. Consulte [Seleccionar la versión del lenguaje C#](../../../language-reference/configure-language-version.md).

En el [repositorio de GitHub de ejemplos de .NET](https://github.com/dotnet/samples/tree/master/csharp/serialization) puede examinar el código de ejemplo en línea.

## <a name="creating-the-loan-object"></a>Crear el objeto Loan

El primer paso consiste en crear una clase `Loan` y una aplicación de consola que use la clase:

1. Cree una aplicación. Escriba `dotnet new console -o serialization` para crear una aplicación de consola en un subdirectorio llamado `serialization`.
1. Abra la aplicación en el editor y agregue una nueva clase denominada `Loan.cs`.
1. Agregue el siguiente código a la clase `Loan`:

[!code-csharp[Loan class definition](../../../../../samples/snippets/csharp/serialization/Loan.cs#1)]

También tendrá que crear una aplicación que use la clase `Loan`.

## <a name="serialize-the-loan-object"></a>Serializar el objeto Loan

1. Abra `Program.cs`. Agregue el código siguiente:

[!code-csharp[Create a loan object](../../../../../samples/snippets/csharp/serialization/Program.cs#1)]

Agregue un controlador de eventos del evento `PropertyChanged` y unas cuantas líneas para modificar el objeto `Loan` y ver los cambios. En el siguiente código puede ver las adiciones realizadas:

[!code-csharp[Listening for the PropertyChanged event](../../../../../samples/snippets/csharp/serialization/Program.cs#2)]

Llegado este punto, puede ejecutar el código y ver el resultado actual:

```console
New customer value: Henry Clay
7.5
7.1
```

Si ejecuta esta aplicación repetidamente, verá que siempre escribe los mismos valores. Se creará un objeto Loan cada vez que ejecute el programa. En el mundo real, las tasas de interés cambian periódicamente, pero no necesariamente cada vez que se ejecuta la aplicación. El código de serialización conlleva que se va a conservar la tasa de interés más reciente entre las instancias de la aplicación. En el paso siguiente, hará esto agregando la serialización a la clase Loan.

## <a name="using-serialization-to-persist-the-object"></a>Usar la serialización para conservar el objeto

Para conservar los valores de la clase Loan, primero debe marcar la clase con el atributo `Serializable`. Agregue el siguiente código encima de la declaración de la clase Loan:

[!code-csharp[Loan class definition](../../../../../samples/snippets/csharp/serialization/Loan.cs#2)]

<xref:System.SerializableAttribute> indica al compilador que todo el contenido de la clase se puede conservar en un archivo. El evento `PropertyChanged` no representa la parte del gráfico de objeto que se debe almacenar, de modo que no se debería serializar. Si lo hace, se serializarían todos los objetos que estén asociados a ese evento. Puede agregar <xref:System.NonSerializedAttribute> a la declaración de campo del controlador de eventos `PropertyChanged`.

[!code-csharp[Disable serialization for the event handler](../../../../../samples/snippets/csharp/serialization/Loan.cs#3)]

A partir de C# 7.3, los atributos se pueden asociar al campo de respaldo de una propiedad implementada automáticamente usando el valor de destino `field`. El siguiente código agrega una propiedad `TimeLastLoaded` y la marca como no serializable:

[!code-csharp[Disable serialization for an auto-implemented property](../../../../../samples/snippets/csharp/serialization/Loan.cs#4)]

El siguiente paso consiste en agregar el código de serialización a la aplicación LoanApp. Para serializar la clase y escribirla en un archivo, usaremos los espacios de nombres <xref:System.IO> y <xref:System.Runtime.Serialization.Formatters.Binary>. Para evitar escribir los nombres completos, puede agregar referencias a los espacios de nombres necesarios, tal y como se muestra en el siguiente código:

[!code-csharp[Adding namespaces for serialization](../../../../../samples/snippets/csharp/serialization/Program.cs#3)]

El siguiente paso es agregar código para deserializar el objeto del archivo cuando el objeto se crea. Agregue una constante a la clase para el nombre de archivo de los datos serializados, tal y como se muestra en el siguiente código:

[!code-csharp[Define the name of the saved file](../../../../../samples/snippets/csharp/serialization/Program.cs#4)]

Luego, agregue el siguiente código después de la línea que crea el objeto `TestLoan`:

[!code-csharp[Read from a file if it exists](../../../../../samples/snippets/csharp/serialization/Program.cs#5)]

Primero hay que confirmar que el archivo existe. Si existe, cree una clase <xref:System.IO.Stream> para leer el archivo binario y una clase <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> para traducirlo. También necesita convertir del tipo de secuencia al tipo de objeto Loan.

Luego, debemos agregar código para serializar la clase en un archivo. Agregue el siguiente código después del código existente en el método `Main`:

[!code-csharp[Save the existing Loan object](../../../../../samples/snippets/csharp/serialization/Program.cs#6)]

En este punto, podrá compilar y ejecutar la aplicación de nuevo. La primera vez que se ejecuta, observe que el tipo de interés comienza en 7.5 y, después, pasa a 7.1. Cierre la aplicación y, después, ejecútela de nuevo. Ahora, la aplicación muestra un mensaje que indica que se ha leído el archivo guardado y la tasa de interés es 7.1 incluso antes del código que la cambia.

## <a name="see-also"></a>Vea también

- [Serialización (C#)](index.md)
- [Guía de programación de C#](../..//index.md)
