---
title: Cambios importantes y las bibliotecas de .NET
description: Procedimientos recomendados para explorar los cambios importantes al crear bibliotecas de .NET.
ms.date: 10/02/2018
ms.openlocfilehash: 2cbd9e0a818b52aede6c9b1f60fdf52dcbd7b96f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79398512"
---
# <a name="breaking-changes"></a>Cambios importantes

Es importante para una biblioteca de .NET buscar el equilibrio entre la estabilidad para los usuarios existentes y la innovación para el futuro. Los creadores de bibliotecas tienden a la refactorización y el replanteamiento de código hasta que es perfecto, pero realizar cambios importantes que afectan a los usuarios existentes tiene un impacto negativo, especialmente para bibliotecas de bajo nivel.

## <a name="project-types-and-breaking-changes"></a>Tipos de proyecto y cambios importantes

El uso que la comunidad de .NET realiza de una biblioteca cambia el efecto de los cambios importantes en los usuarios finales.

- **Las bibliotecas de nivel bajo e intermedio**, como un serializador, un analizador de HTML, un asignador relacional de objetos de base de datos o un marco web, son las más afectadas por cambios importantes.

  Los usuarios finales y otras bibliotecas como dependencias de NuGet usan los paquetes de bloques de creación para desarrollar aplicaciones. Por ejemplo, está creando una aplicación y está usando a un cliente de código abierto para llamar a un servicio web. Una actualización importante a una dependencia que usa el cliente no es algo que pueda solucionar. Debería cambiarse el cliente de código abierto y no tiene control sobre él. Tendrá que buscar versiones compatibles de las bibliotecas o enviar una corrección a la biblioteca de cliente y esperar a una nueva versión. La peor situación posible es si quiere usar dos bibliotecas que dependen de versiones incompatibles de una biblioteca de terceros.

- **Las bibliotecas generales** como un conjunto de controles de IU, son menos sensibles a los cambios importantes.

  En las aplicaciones de usuario final se hace referencia directa a las bibliotecas generales. Si se producen cambios importantes, el desarrollador puede elegir si quiere actualizar a la versión más reciente o puede modificar su aplicación para que funcione con el cambio.

✔️ PIENSE en cómo se va a usar la biblioteca. ¿Qué efectos tendrán los cambios importantes en las aplicaciones y bibliotecas que la usan?

✔️ MINIMICE los cambios importantes al desarrollar una biblioteca de .NET de bajo nivel.

✔️ ES RECOMENDABLE publicar una reescritura importante de una biblioteca como un nuevo paquete NuGet.

## <a name="types-of-breaking-changes"></a>Tipos de cambios importantes

Los cambios importantes se dividen en categorías diferentes y no tienen el mismo impacto.

### <a name="source-breaking-change"></a>Cambios importantes del código fuente

Un cambio importante del código fuente no afecta a la ejecución del programa, pero provocará errores de compilación la próxima vez que se vuelva a compilar la aplicación. Por ejemplo, una nueva sobrecarga puede crear ambigüedad en las llamadas de método que anteriormente no eran ambiguas o un parámetro cuyo nombre ha cambiado interrumpirá a los autores de la llamada que usan parámetros con nombre.

```csharp
public class Task
{
    // Adding a type called Task could conflict with System.Threading.Tasks.Task at compilation
}
```

Como un cambio importante de código fuente solo es perjudicial cuando los desarrolladores vuelven a compilar sus aplicaciones, es el cambio importante menos disruptivo. Los desarrolladores pueden corregir fácilmente su propio código fuente roto.

### <a name="behavior-breaking-change"></a>Cambios importantes del comportamiento

Los cambios de comportamiento son el tipo más común de cambio importante: casi cualquier cambio de comportamiento podría afectar a alguien. Los cambios a la biblioteca, como las firmas de método, las excepciones que se producen o los formatos de datos de entrada o salida, podrían afectar negativamente a los consumidores de la biblioteca. Incluso la corrección de un error podría ser un cambio importante si los usuarios se basaban en el comportamiento con errores anterior.

La incorporación de características y la mejora de comportamientos incorrectos es algo bueno, pero si no se trata con cuidado, realizar la actualización puede resultar muy difícil para los usuarios existentes. Un enfoque para ayudar a los desarrolladores a lidiar con los últimos cambios importantes de comportamiento es ocultarlos en la configuración. La configuración permite a los desarrolladores actualizar a la versión más reciente de la biblioteca y al mismo tiempo utilizar o prescindir de los cambios importantes. Esta estrategia permite a los desarrolladores mantenerse al día al mismo tiempo que permiten que el código que usan se adapte con el tiempo.

Por ejemplo, ASP.NET Core MVC tiene el concepto de una [versión de compatibilidad](/aspnet/core/mvc/compatibility-version) que modifica las características habilitadas y deshabilitadas en `MvcOptions`.

✔️ ES RECOMENDABLE excluir las nuevas características de forma predeterminada si afectan a los usuarios existentes y permitir que los desarrolladores se suscriban a la característica con una opción.

### <a name="binary-breaking-change"></a>Cambios importantes de archivo binario

Un cambio importante de archivo binario se produce al cambiar la API pública de la biblioteca, ya que los ensamblados compilados con versiones anteriores de la biblioteca ya no pueden llamar a la API. Por ejemplo, cambiar la firma de un método mediante la adición de un nuevo parámetro hará que los ensamblados compilados con la versión anterior de la biblioteca inicien una excepción <xref:System.MissingMethodException>.

Un cambio importante de archivo binario también puede afectar a un **ensamblado completo**. Cambiar el nombre de un ensamblado con `AssemblyName` cambiará la identidad del ensamblado, como lo hará agregar, quitar o cambiar la clave de nomenclatura segura del ensamblado. Un cambio de identidad de un ensamblado afectará a todo el código compilado que lo usa.

❌ NO cambie un nombre de ensamblado.

❌ NO agregue, quite ni cambie la clave de nombres seguros.

✔️ ES RECOMENDABLE usar clases base abstractas en lugar de interfaces.

> La adición de algo a una interfaz hará que se produzca un error de los tipos existentes que la implementan. Una clase base abstracta permite agregar una implementación virtual predeterminada.

✔️ ES RECOMENDABLE colocar <xref:System.ObsoleteAttribute> en tipos y miembros que vaya a quitar. El atributo debe tener instrucciones para actualizar el código para dejar de usar la API obsoleta.

> El código que llama a tipos y métodos con el <xref:System.ObsoleteAttribute> generará una advertencia de compilación con el mensaje proporcionado al atributo. Las advertencias proporcionan tiempo suficiente a los usuarios de la API obsoleta para realizar una migración, de modo que cuando se quite la API obsoleta, la mayoría ya no la estará usando.

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

✔️ ES RECOMENDABLE mantener tipos y métodos con <xref:System.ObsoleteAttribute> indefinidamente en las bibliotecas de nivel medio y bajo.

> Quitar API es un cambio de archivo binario. Es recomendable mantener métodos y tipos obsoletos si su mantenimiento es de bajo coste y no agrega mucha deuda técnica a la biblioteca. No quitar tipos y métodos puede ayudar a evitar los peores casos mencionados anteriormente.

## <a name="see-also"></a>Vea también

- [Consideraciones sobre versiones y actualizaciones para desarrolladores de C#](../../csharp/whats-new/version-update-considerations.md)
- [A definitive guide to API-breaking changes in .NET](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net) (Una guía definitiva para cambios importantes de API en .NET)
- [Reglas de cambios importantes de .NET](https://github.com/dotnet/runtime/blob/master/docs/coding-guidelines/breaking-change-rules.md)

>[!div class="step-by-step"]
>[Anterior](versioning.md)
