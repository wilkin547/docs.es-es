---
title: Cambios importantes y las bibliotecas de .NET
description: Prácticas recomendadas para explorar los cambios importantes al crear bibliotecas de. NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 83c01fdad7d836877bf692b87eeb0230219ded36
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2018
ms.locfileid: "49370340"
---
# <a name="breaking-changes"></a>Cambios importantes

Es importante para una biblioteca de .NET buscar un equilibrio entre la estabilidad para los usuarios existentes y la innovación para el futuro. Obtenga información sobre los creadores de bibliotecas hacia la refactorización y replanteamiento de código hasta que es perfecto, pero importantes de los usuarios existentes tiene un impacto negativo, especialmente para bibliotecas de bajo nivel.

## <a name="project-types-and-breaking-changes"></a>Tipos de proyecto y los cambios recientes

Uso de una biblioteca de la Comunidad de .NET cambia el efecto de los principales cambios en los usuarios finales.

* **Baja y bibliotecas de nivel intermedio** al igual que un analizador serializador, HTML, asignador relacional de objetos de base de datos o marco web son las más afectadas por cambios importantes.

  Los paquetes de bloques de creación se usan por el usuario final a los desarrolladores crear aplicaciones y otras bibliotecas como dependencias de NuGet. Por ejemplo, está creando una aplicación y está usando a un cliente de código abierto para llamar a un servicio web. Una actualización de última hora a una dependencia que usa el cliente no es algo que puede corregir. Es el cliente de código abierto que deba cambiarse y no tiene ningún control sobre él. Tendrá que buscar las versiones compatibles de las bibliotecas o enviar una corrección a la biblioteca de cliente y espere a que una nueva versión. La peor situación posible es si desea utilizar dos bibliotecas que dependan de las versiones incompatibles de una biblioteca de terceros.

* **Bibliotecas de alto nivel** como un conjunto de aplicaciones de interfaz de usuario, los controles son menos sensibles a cambios importantes.

  Bibliotecas de alto nivel se hace referencia directamente en una aplicación de usuario final. Si se producen cambios importantes, el desarrollador puede elegir actualizar a la versión más reciente, o puede modificar su aplicación para que funcione con el cambio.

**HACER ✔️** piense en cómo se utilizará la biblioteca. ¿Qué efectos tendrá los cambios importantes en las aplicaciones y bibliotecas que lo usan?

**HACER ✔️** minimizar los cambios importantes al desarrollar una biblioteca de bajo nivel.

**Considere la posibilidad de ✔️** publicación principal reescritura de una biblioteca como un nuevo paquete de NuGet.

## <a name="types-of-breaking-changes"></a>Tipos de cambios importantes

Cambios importantes se dividen en categorías diferentes y no son igualmente impactantes.

### <a name="source-breaking-change"></a>Cambio de origen

Un origen de cambio no afecta a la ejecución del programa, pero provocará errores de compilación la próxima vez que se vuelve a compilar la aplicación. Por ejemplo, una nueva sobrecarga puede crear ambigüedad en las llamadas de método que anteriormente se encontraban ambiguas o un parámetro cuyo nombre ha cambiado interrumpirá los llamadores que utilizan parámetros con nombre.

```csharp
public class Task
{
    // Adding a type called Task could conflict with System.Threading.Tasks.Task at compilation
}
```

Como un origen de cambio importante solo es perjudicial cuando los desarrolladores compilar sus aplicaciones, es el menos disruptivo cambio importante. Los desarrolladores pueden corregir fácilmente su propio código fuente roto.

### <a name="behavior-breaking-change"></a>Cambio de comportamiento

Los cambios de comportamiento son el tipo más común de cambio importante: casi cualquier cambio de comportamiento podría afectar a alguien. Cambia a la biblioteca, como las firmas de método, las excepciones que produce o de entrada o salida formatos de datos, podrían todos afectar negativamente a los consumidores de la biblioteca. Si los usuarios se basaban en el comportamiento previamente dañado, incluso una corrección de errores puede calificar como un cambio importante.

Incorporar características y mejorar los comportamientos incorrectos son algo bueno, pero sin la atención, puede resultar muy difícil para los usuarios existentes que se va a actualizar. Es un enfoque para ayudar a los desarrolladores a lidiar con los últimos cambios de comportamiento ocultarlas detrás de la configuración. La configuración permite a los desarrolladores actualizar a la versión más reciente de la biblioteca mientras al mismo tiempo si elige participar o dejar de participar en cambios importantes. Esta estrategia permite a los desarrolladores a mantenerse al día al permitir que su código usado adaptarse con el tiempo.

Por ejemplo, ASP.NET Core MVC tiene el concepto de un [versión compatibilidad](/aspnet/core/mvc/compatibility-version) que modifica las características habilitadas y deshabilitadas en `MvcOptions`.

**Considere la posibilidad de ✔️** excluyendo las nuevas características de forma predeterminada, si afectan a los usuarios existentes y permiten que los desarrolladores a participar en la característica con una configuración.

### <a name="binary-breaking-change"></a>Cambio importante binario

Se produce un cambio de archivo binario cuando cambie la API pública de la biblioteca, por lo que los ensamblados compilados con versiones anteriores de la biblioteca ya no sean pueden llamar a la API. Por ejemplo, cambiar la firma de un método mediante la adición de un nuevo parámetro hará que los ensamblados compilados con la versión anterior de la biblioteca producir un <xref:System.MissingMethodException>.

Un cambio de archivo binario también puede interrumpir un **todo el ensamblado**. Cambiar el nombre de un ensamblado con `AssemblyName` cambiará la identidad del ensamblado, así como agregar, quitar o cambiar la clave de nomenclatura segura del ensamblado. Un cambio de identidad de un ensamblado interrumpirá en todo el código compilado que lo usa.

**❌ NO** cambiar un nombre de ensamblado.

**NO ❌** agregar, quitar o cambiar la clave de nomenclatura segura.

**Considere la posibilidad de ✔️** mediante clases base abstractas en lugar de interfaces.

> Agrega algo a una interfaz hará que los tipos existentes que implementan un error. Una clase base abstracta permite agregar una implementación virtual predeterminada.

**Considere la posibilidad de ✔️** colocar el <xref:System.ObsoleteAttribute> en tipos y miembros que se va a quitar. El atributo debe tener instrucciones para actualizar el código para dejar de usar la API obsoleta.

> Código que llama a tipos y métodos con el <xref:System.ObsoleteAttribute> generará una advertencia de compilación con el mensaje proporcionado para el atributo. Las personas de dar advertencias que use el tiempo de superficie de API obsoleto para migrar de modo que cuando se quita la API obsoleta, la mayoría ya no está usando.

```csharp
public class Document
{
    [Obsolete("LoadDocument(string) is obsolete. Use LoadDocument(Uri) instead.")]
    public static Document LoadDocument(string uri)
    {
        return LoadDocument(new Uri(uri));
    }

    public static Document LoadDocument(Uri uri)
    {
        // Load the document
    }
}
```

## <a name="see-also"></a>Vea también

* [Consideraciones sobre la versión y actualización para los desarrolladores de C#](../../csharp/whats-new/version-update-considerations.md)
* [Una guía definitiva para cambios importantes de la API de .NET](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net)
* [Reglas de cambio de salto de CoreFX](https://github.com/dotnet/corefx/blob/master/Documentation/coding-guidelines/breaking-change-rules.md)

>[!div class="step-by-step"]
[Anterior](./versioning.md)
