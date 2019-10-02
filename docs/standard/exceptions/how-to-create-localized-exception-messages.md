---
title: 'Procedimiento para: Crear excepciones definidas por el usuario con mensajes de excepción localizados'
description: Obtenga información sobre cómo crear excepciones definidas por el usuario con mensajes de excepción localizados.
author: Youssef1313
ms.author: ronpet
ms.date: 09/13/2019
ms.openlocfilehash: 1e5ef5658e4cb71d0689a1786494eaec57d4e7fb
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332966"
---
# <a name="how-to-create-user-defined-exceptions-with-localized-exception-messages"></a>Procedimiento para: Crear excepciones definidas por el usuario con mensajes de excepción localizados

En este artículo, obtendrá información sobre cómo crear excepciones definidas por el usuario que se hereden de la clase base <xref:System.Exception> con mensajes de excepción localizados mediante ensamblados satélite.

## <a name="create-custom-exceptions"></a>Creación de excepciones personalizadas

.NET contiene muchas excepciones distintas que puede usar. Sin embargo, en algunos casos, cuando ninguna de ellas satisface sus necesidades, puede crear sus propias excepciones personalizadas.

Supongamos que desea crear un `StudentNotFoundException` que contiene una propiedad `StudentName`.
Para crear una excepción personalizada, siga estos pasos:

1. Cree una clase serializable que herede de <xref:System.Exception>. El nombre de clase debe terminar en "Exception":

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception { }
    ```

1. Agregue los constructores predeterminados:

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception
    {
        public StudentNotFoundException() { }

        public StudentNotFoundException(string message)
            : base(message) { }

        public StudentNotFoundException(string message, Exception inner)
            : base(message, inner) { }
    }
    ```

1. Defina cualquier propiedad y constructores adicionales:

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception
    {
        public string StudentName { get; }

        public StudentNotFoundException() { }

        public StudentNotFoundException(string message)
            : base(message) { }

        public StudentNotFoundException(string message, Exception inner)
            : base(message, inner) { }

        public StudentNotFoundException(string message, string studentName)
            : this(message)
        {
            StudentName = studentName;
        }
    }
    ```

## <a name="create-localized-exception-messages"></a>Creación de mensajes de excepción localizados

Creó una excepción personalizada y puede iniciarla en cualquier parte con código como el siguiente:

```csharp
throw new StudentNotFoundException("The student cannot be found.", "John");
```

El problema con la línea anterior es que "No se encuentra el alumno" no es más que una cadena constante. En una aplicación localizada, quiere tener mensajes diferentes en función de la referencia cultural del usuario.
Los [ensamblados satélite](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md) son una buena manera de hacerlo. Un ensamblado satélite es un archivo .dll que contiene recursos para un idioma específico. Cuando se solicitan recursos específicos en tiempo de ejecución, el CLR encuentra ese recurso en función de la referencia cultural del usuario. Si no se encuentra ningún ensamblado satélite para esa referencia cultural, se usan los recursos de la referencia cultural predeterminada.

Para crear los mensajes de excepción localizados:

1. Cree una carpeta llamada *Recursos* para contener los archivos de recursos.
1. Agréguele un archivo de recursos nuevo. Para ello, en Visual Studio, haga clic con el botón derecho en la carpeta en el **Explorador de soluciones** y seleccione **Agregar** -> **Nuevo elemento** -> **Archivo de recursos**. Asígnele al archivo el nombre *ExceptionMessages.resx*. Este es el archivo de recursos predeterminado.
1. Agregue un par nombre-valor para el mensaje de excepción, como se muestra en la imagen siguiente: ![Agregar recursos a la referencia cultural predeterminada](media/add-resources-to-default-culture.jpg)
1. Agregue un archivo de recursos nuevo para francés. Asígnele el nombre *ExceptionMessages.fr-FR.resx*.
1. Vuelva a agregar un par nombre-valor para el mensaje de excepción, pero con un valor en francés: ![Agregar recursos a la referencia cultural fr-FR](media/add-resources-to-fr-culture.jpg)
1. Después de compilar el proyecto, la carpeta de la salida de compilación debe contener la carpeta *fr-FR* con un archivo *.dll*, que es el ensamblado satélite.
1. Inicia la excepción con código como el siguiente:

    ```csharp
    var resourceManager = new ResourceManager("FULLY_QIALIFIED_NAME_OF_RESOURCE_FILE", Assembly.GetExecutingAssembly());
    throw new StudentNotFoundException(resourceManager.GetString("StudentNotFound"), "John");
    ```

  > [!NOTE]
  > Si el nombre del proyecto es `TestProject` y el archivo de recursos *ExceptionMessages.resx* reside en la carpeta *Recursos* del proyecto, el nombre completo del archivo de recursos es `TestProject.Resources.ExceptionMessages`.

## <a name="see-also"></a>Vea también

- [Cómo crear excepciones definidas por el usuario](how-to-create-user-defined-exceptions.md)
- [Crear ensamblados satélite para aplicaciones de escritorio](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md)
- [base (Referencia de C#)](../../csharp/language-reference/keywords/base.md)
- [this (Referencia de C#)](../../csharp/language-reference/keywords/this.md)
