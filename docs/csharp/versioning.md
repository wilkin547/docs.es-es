---
title: 'Control de versiones de C#: Guía de C#'
description: Comprender cómo funciona el control de versiones en C# y .NET
ms.date: 01/08/2017
ms.technology: csharp-advanced-concepts
ms.assetid: aa8732d7-5cd0-46e1-994a-78017f20d861
ms.openlocfilehash: dc192337e4eaa5f9f1d6509ea8c15deeac34a48c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645452"
---
# <a name="versioning-in-c"></a>Control de versiones en C\#

En este tutorial, obtendrá información sobre qué significa el control de versiones en .NET. También obtendrá información sobre los factores que deben tenerse en cuenta para controlar las versiones de su biblioteca así como para actualizar a una versión nueva de esta.

## <a name="authoring-libraries"></a>Creación de bibliotecas

Como desarrollador que ha creado bibliotecas de .NET para uso público, probablemente se ha encontrado en situaciones en las que tiene que implementar nuevas actualizaciones. Cómo realizar este proceso es muy importante, ya que necesita asegurarse de que existe una transición sin problemas del código existente a la versión nueva de su biblioteca. Aquí se muestran algunos aspectos para tener en cuenta a la hora de crear una versión nueva:

### <a name="semantic-versioning"></a>Control de versiones semántico

[Control de versiones semántico](https://semver.org/) (SemVer para abreviar) es una convención de nomenclatura que se aplica a las versiones de su biblioteca para indicar eventos importantes específicos.
De manera ideal, la información de la versión que proporciona a la biblioteca debe ayudar a los desarrolladores a determinar la compatibilidad con sus proyectos que usan versiones anteriores de la misma biblioteca.

El enfoque más sencillo de SemVer es el formato de 3 componentes `MAJOR.MINOR.PATCH`, donde:

- `MAJOR` se incrementa cuando realiza cambios de API incompatibles
- `MINOR` se incrementa cuando agrega funciones de manera compatible con versiones anteriores
- `PATCH` se incrementa cuando realiza correcciones de errores compatibles con versiones anteriores

También existen maneras de especificar otros escenarios como versiones preliminares, etc. al aplicar información de la versión a su biblioteca .NET.

### <a name="backwards-compatibility"></a>Compatibilidad con versiones anteriores

A medida que presente versiones nuevas de su biblioteca, la compatibilidad con las versiones anteriores será probablemente una de sus mayores preocupaciones.
Una versión nueva de su biblioteca es compatible en su origen con una versión anterior si el código que depende de la versión anterior, puede, cuando se vuelve a compilar, trabajar con la versión nueva.
Una versión nueva de su biblioteca tiene compatibilidad binaria si una aplicación que dependía de la versión anterior, puede, sin que se vuelva a compilar, trabajar con la versión nueva.

Aquí se muestran algunos aspectos a tener en cuenta al intentar mantener la compatibilidad con versiones anteriores de su biblioteca:

- Métodos virtuales: cuando hace que un método virtual sea no virtual en la versión nueva, significa que los proyectos que reemplacen ese método tendrán que actualizarse. Esto es un cambio brusco enorme y se desaconseja totalmente.
- Firmas de método: cuando actualizar un comportamiento del método requiere que también se cambie su firma, en su lugar se debe crear una sobrecarga de manera que el código que llama a ese método siga funcionando.
Siempre puede manipular la firma del método anterior para llamar a la firma del método nuevo, de manera que la implementación siga siendo coherente.
- [Atributo obsoleto](language-reference/attributes/general.md#obsolete-attribute): puede usar este atributo en el código para especificar clases o miembros de clases que han quedado obsoletos y que probablemente se quiten en versiones futuras. Esto garantiza que los desarrolladores que usen su biblioteca estén mejor preparados para los cambios bruscos.
- Argumentos de método opcionales: cuando hace que los argumentos de método opcionales anteriores sean obligatorios o cambien su valor predeterminado, se tendrá que actualizar todo el código que no proporcione esos argumentos.

> [!NOTE]
> Hacer que los argumentos obligatorios sean opcionales debe tener un efecto muy pequeño, especialmente si no cambia el comportamiento del método.

Cuánto más facilite la actualización a la nueva versión de la biblioteca a sus usuarios, más rápidamente la actualizarán.

### <a name="application-configuration-file"></a>Archivo de configuración de aplicación

Como desarrollador de .NET, existe una posibilidad muy alta de que haya encontrado [el archivo `app.config`](../framework/configure-apps/file-schema/index.md) en la mayoría de tipos de proyecto.
Este sencillo archivo de configuración puede hacer mucho por mejorar la implementación de las actualizaciones nuevas. Generalmente, debe diseñar sus bibliotecas de tal manera que la información que es probable que cambie regularmente se almacene en el archivo `app.config`, de esta manera, cuando dicha información se actualice, el archivo de configuración de las versiones anteriores solo necesita reemplazarse por el nuevo sin necesidad de volver a compilar la biblioteca.

## <a name="consuming-libraries"></a>Consumo de bibliotecas

Como desarrollador que consume bibliotecas .NET creadas por otros desarrolladores, es probable que sea consciente de que una nueva versión de una biblioteca puede que no sea completamente compatible con su proyecto y, a menudo, puede que tenga que actualizar su código para trabajar con esos cambios.

Por suerte, C# y el ecosistema de .NET incluyen características y técnicas que nos permiten actualizar fácilmente nuestra aplicación para que funcione con las versiones nuevas de bibliotecas que pueden presentar cambios bruscos.

### <a name="assembly-binding-redirection"></a>Redirección de enlace de ensamblados

Puede usar el archivo *app.config* para actualizar la versión de una biblioteca que use su aplicación. Al agregar lo que se denomina una [*redirección de enlace*](../framework/configure-apps/redirect-assembly-versions.md), se puede usar la nueva versión de la biblioteca sin tener que volver a compilar la aplicación. En el siguiente ejemplo se muestra cómo actualizaría el archivo *app.config* de la aplicación para usar la versión de revisión `1.0.1` de `ReferencedLibrary`, en lugar de la versión `1.0.0` con la que se ha compilado originalmente.

```xml
<dependentAssembly>
    <assemblyIdentity name="ReferencedLibrary" publicKeyToken="32ab4ba45e0a69a1" culture="en-us" />
    <bindingRedirect oldVersion="1.0.0" newVersion="1.0.1" />
</dependentAssembly>
```

> [!NOTE]
> Este enfoque solo funcionará si la versión nueva de `ReferencedLibrary` tiene compatibilidad binaria con su aplicación.
> Vea la sección anterior [Compatibilidad con versiones anteriores](#backwards-compatibility) para ver los cambios que debe tener en cuenta al determinar la compatibilidad.

### <a name="new"></a>new

Use el modificador `new` para ocultar los miembros heredados de una clase base. Esta es una manera en la que las clases derivadas pueden responder a las actualizaciones en clases base.

Considere el ejemplo siguiente:

[!code-csharp[Sample usage of the 'new' modifier](~/samples/snippets/csharp/versioning/new/Program.cs#sample)]

**Salida**

```console
A base method
A derived method
```

En el ejemplo anterior puede ver cómo `DerivedClass` oculta el método `MyMethod` presente en `BaseClass`.
Esto significa que cuando una clase base en la versión nueva de una biblioteca agrega un miembro que ya existe en su clase derivada, simplemente puede usar el modificador `new` en su miembro de clase derivada para ocultar el miembro de clase base.

Cuando no se especifica ningún modificador `new`, una clase derivada ocultará de manera predeterminada los miembros en conflicto de una clase base, aunque se generará una advertencia del compilador, el código se compilará. Esto significa que agregar simplemente miembros nuevos a una clase existente, hace que la versión nueva de su biblioteca tenga compatibilidad binaria y de origen con el código que depende de ella.

### <a name="override"></a>override

El modificador `override` significa que una implementación derivada extiende la implementación de un miembro de clase base en lugar de ocultarlo. El miembro de clase base necesita que se le aplique el modificador `virtual`.

[!code-csharp[Sample usage of the 'override' modifier](../../samples/snippets/csharp/versioning/override/Program.cs#sample)]

**Salida**

```console
Base Method One: Method One
Derived Method One: Derived Method One
```

El modificador `override` se evalúa en tiempo de compilación y el compilador producirá un error si no encuentra un miembro virtual que reemplazar.

Su conocimiento de las técnicas que se han tratado y su comprensión de las situaciones en las cuales usarlas, contribuirá en gran medida a facilitar la transición entre las versiones de una biblioteca.
