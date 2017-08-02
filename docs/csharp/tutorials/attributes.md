---
title: 'Atributos: C#'
description: "Aprenda cómo funcionan los atributos en C#."
keywords: .NET, .NET Core, C#, atributos
author: mgroves
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: b152cf36-76e4-43a5-b805-1a1952e53b79
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cc8f38d96f7f1c41f04d64c2acc2f53805b6b012
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="using-attributes-in-c"></a>Uso de atributos en C# #

Los atributos proporcionan una manera de asociar la información con el código de manera declarativa. También pueden proporcionar un elemento reutilizable que se puede aplicar a diversos destinos.

Considere el atributo `[Obsolete]`. Se puede aplicar a clases, structs, métodos, constructores y más. _Declara_ que el elemento está obsoleto. Es decisión del compilador de C# buscar este atributo y realizar alguna acción como respuesta.

En este tutorial, se le introducirá a cómo agregar atributos al código, cómo crear y usar sus propios atributos y cómo usar algunos atributos que se integran en .NET Core.

## <a name="prerequisites"></a>Requisitos previos
Deberá configurar la máquina para ejecutar .NET Core. Puede encontrar las instrucciones de instalación en la página de [.NET Core](https://www.microsoft.com/net/core).
Puede ejecutar esta aplicación en Windows, Ubuntu Linux, macOS o en un contenedor de Docker. Deberá instalar su editor de código favorito. En las siguientes descripciones se usa [Visual Studio Code](https://code.visualstudio.com/), que es un editor multiplataforma de código abierto. Sin embargo, puede usar las herramientas que le resulten más cómodas.

## <a name="create-the-application"></a>Crear la aplicación

Ahora que ha instalado todas las herramientas, cree una nueva aplicación de .NET Core. Para usar el generador de línea de comandos, ejecute el siguiente comando en su shell favorito:

`dotnet new console`

Este comando creará archivos de proyecto esenciales de .NET Core. Debe ejecutar `dotnet restore` para restaurar las dependencias necesarias para compilar este proyecto.

Para ejecutar el programa, use `dotnet run`. Deberá ver la salida "Hola a todos" a la consola.

## <a name="how-to-add-attributes-to-code"></a>Cómo agregar atributos al código

En C#, los atributos son clases que se heredan de la clase base `Attribute`. Cualquier clase que se hereda de `Attribute` puede usarse como una especie de "etiqueta" en otros fragmentos de código.
Por ejemplo, hay un atributo llamado `ObsoleteAttribute`,  que se usa para indicar que el código está obsoleto y ya no debe utilizarse. Puede colocar este atributo en una clase, por ejemplo, mediante corchetes.

[!code-csharp[Ejemplo de atributo obsoleto](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ObsoleteExample1)]  

Tenga en cuenta que, mientras que la clase se denomina `ObsoleteAttribute`, solo es necesario usar `[Obsolete]` en el código. Se trata de una convención que sigue C#.
Puede usar el nombre completo `[ObsoleteAttribute]` si así lo prefiere.

Cuando se marca una clase como obsoleta, es una buena idea proporcionar alguna información de *por qué* es obsoleta, o *qué* usar en su lugar. Para ello se pasa un parámetro de cadena al atributo obsoleto.

[!code-csharp[Ejemplo de atributo obsoleto con parámetros](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ObsoleteExample2)]

La cadena se pasa como argumento a un constructor `ObsoleteAttribute`, como si estuviera escribiendo `var attr = new ObsoleteAttribute("some string")`.

Los parámetros a un constructor de atributos se limitan a literales o tipos simples: `bool, int, double, string, Type, enums, etc` y matrices de esos tipos.
No se puede usar una expresión o una variable. Es libre de usar parámetros posicionales o con nombre.

## <a name="how-to-create-your-own-attribute"></a>Cómo crear su propio atributo

Crear un atributo es tan sencillo como heredarlo de la clase base `Attribute`.

[!code-csharp[Crear su propio atributo](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#CreateAttributeExample1)]

Con lo anterior, ahora puedo usar `[MySpecial]` (o `[MySpecialAttribute]`) como un atributo en otra parte de la base de código.

[!code-csharp[Uso de su propio atributo](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#CreateAttributeExample2)]

Los atributos de la biblioteca de clases base de .NET como `ObsoleteAttribute` desencadenan ciertos comportamientos en el compilador. Sin embargo, cualquier atributo que cree funcionará como metadatos y no tendrá como resultado ningún código dentro de la clase de atributo que se ejecuta. Es decisión suya actuar sobre esos metadatos en otra parte del código (más adelante en este tutorial se hablará sobre ello).

Aquí hay un problema que se debe vigilar. Como se mencionó anteriormente, solo determinados tipos se puedan pasar como argumentos al usar atributos. Sin embargo, al crear un tipo de atributo, el compilador de C# no le impedirá crear esos parámetros. En el ejemplo siguiente, he creado un atributo con un constructor que se compila correctamente.

[!code-csharp[Constructor válido usado en un atributo](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeGothca1)]

Sin embargo, no podrá usar este constructor con una sintaxis de atributo.

[!code-csharp[Intento no válido de usar el constructor de atributos](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeGotcha2)]

Lo anterior provocará un error de compilador como `Attribute constructor parameter 'myClass' has type 'Foo', which is not a valid attribute parameter type`.

## <a name="how-to-restrict-attribute-usage"></a>Cómo restringir el uso de atributos

Los atributos pueden usarse en varios destinos. Los ejemplos anteriores los muestran en las clases, pero ahora se pueden usar en:

* Ensamblado
* Clase
* Constructor
* Delegate
* Enum
* Evento
* Campo
* GenericParameter
* Interfaz
* Método
* Módulo
* Parámetro
* Propiedad
* ReturnValue
* Struct

Cuando se crea una clase de atributo, de forma predeterminada C# podrá usar ese atributo en cualquiera de los destinos de atributo posibles. Si desea restringir el atributo a determinados destinos, puede hacerlo mediante la clase de atributo `AttributeUsageAttribute`. ¡Sí, un atributo en un atributo!

[!code-csharp[Uso de su propio atributo](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeUsageExample1)]

Si intenta colocar el atributo anterior en algo que no sea una clase o un struct, obtendrá un error del compilador como `Attribute 'MyAttributeForClassAndStructOnly' is not valid on this declaration type. It is only valid on 'class, struct' declarations`.

[!code-csharp[Uso de su propio atributo](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeUsageExample2)]

## <a name="how-to-use-attributes-attached-to-a-code-element"></a>Cómo usar los atributos asociados a un elemento de código

Los atributos actúan como metadatos. Sin algo de fuerza exterior, no harían realmente nada.

Para buscar y actuar sobre los atributos, se requiere en general [reflexión](../programming-guide/concepts/reflection.md). En este tutorial no se tratará la reflexión de forma detallada, pero la idea básica es que la reflexión le permite escribir código en C# que examina otro código.

Por ejemplo, puede usar reflexión para obtener información sobre una clase: 

[!code-csharp[Obtención de información de tipos con reflexión](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ReflectionExample1)]

La salida será algo como esto: `The assembly qualified name of MyClass is ConsoleApplication.MyClass, attributes, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null`.

Una vez que tenga un objeto `TypeInfo` (o un elemento `MemberInfo`, `FieldInfo`, etc.), puede usar el método `GetCustomAttributes`. Este devolverá una colección de objetos `Attribute`.
También puede usar `GetCustomAttribute` y especificar un tipo de atributo.

Este es un ejemplo del uso de `GetCustomAttributes` en una instancia de `MemberInfo` para `MyClass` (que anteriormente vimos que contiene un atributo `[Obsolete]`).

[!code-csharp[Obtención de información de tipos con reflexión](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ReflectionExample2)]

Eso se imprimirá en la consola: `Attribute on MyClass: ObsoleteAttribute`. Intente agregar otros atributos a `MyClass`.

Es importante tener en cuenta que se crean instancias de estos objetos `Attribute` de forma diferida. Es decir, no podrá crea una instancia de ellos hasta que use `GetCustomAttribute` o `GetCustomAttributes`.
También se crea una instancia de ellos cada vez. Al llamar a `GetCustomAttributes` dos veces en una fila se devuelven dos instancias diferentes de `ObsoleteAttribute`.

## <a name="common-attributes-in-the-base-class-library-bcl"></a>Atributos comunes en la biblioteca de clases base (BCL)

Muchas herramientas y marcos de trabajo emplean atributos. NUnit usa atributos como `[Test]` y `[TestFixture]` que son utilizados por la serie de pruebas NUnit. ASP.NET MVC usa atributos como `[Authorize]` y proporciona un marco de filtro de acción para ejecutar problemas transversales en acciones de MVC. [PostSharp](https://www.postsharp.net) usa la sintaxis de atributo para permitir la programación en C# orientada a aspectos.

Estos son algunos atributos importantes integrados en las bibliotecas de clases base de .NET Core:

* `[Obsolete]`. Este se usó en los ejemplos anteriores, y se encuentra en el espacio de nombres `System`. Es útil proporcionar documentación declarativa sobre una base de código cambiante. Se puede proporcionar un mensaje en forma de cadena, y se puede usar otro parámetro booleano para escalarlo de una advertencia del compilador a un error del compilador.

* `[Conditional]`. Este atributo está en el espacio de nombres `System.Diagnostics`. Este atributo se puede aplicar a métodos (o clases de atributos). Debe pasar una cadena al constructor.
Si esa cadena coincide con una directiva `#define`, el compilador de C# quitará las llamadas a ese método (pero no el método propiamente dicho). Normalmente se usa con fines de depuración (diagnósticos).

* `[CallerMemberName]`. Este atributo se puede usar en parámetros, y reside en el espacio de nombres `System.Runtime.CompilerServices`. Es un atributo que se usa para inyectar el nombre del método que llama a otro método. Esto se usa normalmente como una manera de eliminar "cadenas mágicas" al implementar INotifyPropertyChanged en distintos marcos de interfaz de usuario. Por ejemplo:

[!code-csharp[Uso de CallerMemberName al implementar INotifyPropertyChanged](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#CallerMemberName1)]

En el código anterior, no necesita tener una cadena `"Name"` de literal. Esto puede ayudar a impedir errores relacionados con los tipos y también agiliza los procesos de refactorización o cambio de nombre.

## <a name="summary"></a>Resumen

Los atributos dotan de eficacia declarativa a C#. Pero son una forma de código, como los metadatos, y no actúan por sí mismos.

