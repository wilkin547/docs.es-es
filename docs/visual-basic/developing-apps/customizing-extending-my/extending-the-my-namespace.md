---
title: Extender el espacio de nombres My en Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.AddingMyExtensions
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
ms.openlocfilehash: 6da0914c9d2d4dc1220ede5d6fa9f1aa6b43426a
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775301"
---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Extender el espacio de nombres `My` en Visual Basic

El espacio de nombres `My` de Visual Basic expone propiedades y métodos que le permiten aprovechar fácilmente la eficacia de la .NET Framework. El espacio de nombres `My` simplifica los problemas comunes de programación, lo que a menudo reduce una tarea difícil a una sola línea de código. Además, el espacio de nombres `My` es totalmente extensible, por lo que puede personalizar el comportamiento de `My` y agregar nuevos servicios a su jerarquía para adaptarse a las necesidades específicas de la aplicación. En este tema se explica cómo personalizar los miembros existentes del espacio de nombres `My` y cómo agregar sus propias clases personalizadas al espacio de nombres `My`.

## <a name="customizing-existing-my-namespace-members"></a>Personalización de los miembros de espacio de nombres `My` existentes

El espacio de nombres `My` de Visual Basic expone información de uso frecuente sobre su aplicación, su equipo, etc. Para obtener una lista completa de los objetos del espacio de nombres `My`, vea [mi referencia](../../language-reference/keywords/my-reference.md). Es posible que tenga que personalizar los miembros existentes del espacio de nombres `My` de modo que se ajusten mejor a las necesidades de la aplicación. Cualquier propiedad de un objeto en el espacio de nombres `My` que no sea de solo lectura se puede establecer en un valor personalizado.

Por ejemplo, suponga que utiliza con frecuencia el objeto `My.User` para tener acceso al contexto de seguridad actual para el usuario que ejecuta la aplicación. Sin embargo, su empresa usa un objeto de usuario personalizado para exponer información adicional y capacidades para los usuarios de la empresa. En este escenario, puede reemplazar el valor predeterminado de la propiedad `My.User.CurrentPrincipal` por una instancia de su propio objeto de entidad de seguridad personalizada, como se muestra en el ejemplo siguiente:

[!code-vb[VbVbcnExtendingMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#1)]

Al establecer la propiedad `CurrentPrincipal` en el objeto `My.User`, cambia la identidad en la que se ejecuta la aplicación. El objeto `My.User`, a su vez, devuelve información sobre el usuario recién especificado.
  
## <a name="adding-members-to-my-objects"></a>Agregar miembros a objetos `My`

Los tipos devueltos de `My.Application` y `My.Computer` se definen como clases `Partial`. Por consiguiente, puede extender los objetos `My.Application` y `My.Computer` creando una clase de `Partial` denominada `MyApplication` o `MyComputer`. La clase no puede ser una clase `Private`. Si especifica la clase como parte del espacio de nombres `My`, puede Agregar propiedades y métodos que se incluirán con los objetos `My.Application` o `My.Computer`.

En el ejemplo siguiente se agrega una propiedad denominada `DnsServerIPAddresses` al objeto `My.Computer`:

[!code-vb[VbVbcnExtendingMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class2.vb#2)]

## <a name="adding-custom-objects-to-the-my-namespace"></a>Agregar objetos personalizados al espacio de nombres `My`

Aunque el espacio de nombres `My` proporciona soluciones para muchas tareas de programación comunes, puede encontrar tareas que el espacio de nombres `My` no soluciona. Por ejemplo, la aplicación podría tener acceso a los servicios de directorio personalizados para los datos de usuario, o bien la aplicación podría utilizar ensamblados que no se instalan de forma predeterminada con Visual Basic. Puede extender el espacio de nombres `My` para incluir soluciones personalizadas a las tareas comunes que son específicas de su entorno. El espacio de nombres `My` se puede ampliar fácilmente para agregar nuevos miembros a fin de satisfacer las necesidades crecientes de las aplicaciones. Además, puede implementar las extensiones de espacio de nombres de `My` para otros desarrolladores como una plantilla de Visual Basic.
  
### <a name="adding-members-to-the-my-namespace"></a>Agregar miembros al espacio de nombres `My`

Dado que `My` es un espacio de nombres como cualquier otro espacio de nombres, puede agregarle propiedades de nivel superior simplemente agregando un módulo y especificando un `Namespace` de `My`. Anote el módulo con el atributo `HideModuleName` como se muestra en el ejemplo siguiente. El atributo `HideModuleName` garantiza que IntelliSense no mostrará el nombre del módulo cuando muestre los miembros del espacio de nombres `My`.

[!code-vb[VbVbcnExtendingMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#3)]

Para agregar miembros al espacio de nombres `My`, agregue las propiedades según sea necesario al módulo. Para cada propiedad agregada al espacio de nombres `My`, agregue un campo privado de tipo `ThreadSafeObjectProvider(Of T)`, donde el tipo es el tipo devuelto por la propiedad personalizada. Este campo se usa para crear instancias de objetos seguros para subprocesos que la propiedad devolverá llamando al método `GetInstance`. Como resultado, cada subproceso que tiene acceso a la propiedad extendida recibe su propia instancia del tipo devuelto. En el ejemplo siguiente se agrega una propiedad denominada `SampleExtension` que es de tipo `SampleExtension` al espacio de nombres `My`:

[!code-vb[VbVbcnExtendingMy#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#4)]

## <a name="adding-events-to-custom-my-objects"></a>Agregar eventos a objetos de `My` personalizados

Puede usar el objeto `My.Application` para exponer eventos para los objetos `My` personalizados extendiendo la `MyApplication` clase parcial en el espacio de nombres `My`. En el caso de los proyectos basados en Windows, puede hacer doble clic en el nodo **mi proyecto** en para el proyecto en **Explorador de soluciones**. En el **Diseñador de proyectos**de Visual Basic, haga clic en la pestaña **aplicación** y, a continuación, haga clic en el botón **ver eventos de aplicaciones** . Se creará un nuevo archivo denominado *ApplicationEvents. VB* . Contiene el código siguiente para extender la clase `MyApplication`:

[!code-vb[VbVbcnExtendingMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#5)]

Puede agregar controladores de eventos para los objetos de `My` personalizados agregando controladores de eventos personalizados a la clase `MyApplication`. Los eventos personalizados permiten agregar código que se ejecutará cuando se agregue o se quite un controlador de eventos, o cuando se genere el evento. Tenga en cuenta que el código de `AddHandler` para un evento personalizado solo se ejecuta si un usuario agrega el código para controlar el evento. Por ejemplo, considere que el objeto `SampleExtension` de la sección anterior tiene un evento `Load` para el que desea agregar un controlador de eventos personalizado. En el ejemplo de código siguiente se muestra un controlador de eventos personalizado denominado `SampleExtensionLoad` que se invocará cuando se produzca el evento de `My.SampleExtension.Load`. Cuando se agrega código para controlar el nuevo evento `My.SampleExtensionLoad`, se ejecuta la parte `AddHandler` de este código de evento personalizado. El método `MyApplication_SampleExtensionLoad` se incluye en el ejemplo de código para mostrar un ejemplo de un controlador de eventos que controla el evento `My.SampleExtensionLoad`. Tenga en cuenta que el evento `SampleExtensionLoad` estará disponible al seleccionar la opción **mis eventos de aplicación** en la lista desplegable de la izquierda situada encima del editor de código cuando se edita el archivo *ApplicationEvents. VB* .

[!code-vb[VbVbcnExtendingMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#6)]

## <a name="design-guidelines"></a>Directrices de diseño

Al desarrollar extensiones para el espacio de nombres `My`, utilice las siguientes directrices para ayudar a minimizar los costos de mantenimiento de los componentes de extensión:

- **Incluya solo la lógica de la extensión.** La lógica incluida en la extensión de espacio de nombres `My` debe incluir solo el código necesario para exponer la funcionalidad necesaria en el espacio de nombres `My`. Dado que la extensión residirá en los proyectos de usuario como código fuente, la actualización del componente de extensión incurrirá en un alto costo de mantenimiento y se debe evitar si es posible.
- **Minimizar suposiciones de proyecto.** Al crear las extensiones del espacio de nombres `My`, no asuma un conjunto de referencias, importaciones de nivel de proyecto o configuraciones de compilador específicas (por ejemplo, `Option Strict` desactivada). En su lugar, minimice las dependencias y califique totalmente todas las referencias de tipos mediante la palabra clave `Global`. Además, asegúrese de que la extensión se compila con `Option Strict` activado para minimizar los errores de la extensión.
- **Aísle el código de la extensión.** Al colocar el código en un único archivo, la extensión se podrá implementar fácilmente como una plantilla de elemento de Visual Studio. Para obtener más información, vea "empaquetar e implementar extensiones" más adelante en este tema. Colocar todos los `My` código de extensión de espacio de nombres en un solo archivo o en una carpeta independiente de un proyecto también ayudará a los usuarios a encontrar la extensión de espacio de nombres `My`.

## <a name="designing-class-libraries-for-my"></a>Diseñar bibliotecas de clases para `My`

Como es el caso de la mayoría de los modelos de objetos, algunos modelos de diseño funcionan bien en el espacio de nombres `My` y otros no. Al diseñar una extensión para el espacio de nombres `My`, tenga en cuenta los siguientes principios:

- **Métodos sin estado.** Los métodos del espacio de nombres `My` deben proporcionar una solución completa a una tarea específica. Asegúrese de que los valores de parámetro que se pasan al método proporcionan toda la entrada necesaria para completar la tarea en cuestión. Evite crear métodos que se basen en el estado anterior, como conexiones abiertas a recursos.
- **Instancias globales.** El único Estado que se mantiene en el espacio de nombres `My` es global en el proyecto. Por ejemplo, `My.Application.Info` encapsula el estado que se comparte en toda la aplicación.
- **Tipos de parámetros simples.** Evite las cosas sencillas evitando tipos de parámetro complejos. En su lugar, cree métodos que no tomen ninguna entrada de parámetros o que tomen tipos de entrada simples como cadenas, tipos primitivos, etc.
- **Métodos de generador.** Algunos tipos son necesariamente difíciles de crear instancias. Proporcionar métodos de fábrica como extensiones para el espacio de nombres `My` permite detectar y consumir más fácilmente los tipos que se encuentran en esta categoría. Un ejemplo de un Factory Method que funciona bien es `My.Computer.FileSystem.OpenTextFileReader`. Hay varios tipos de secuencias disponibles en el .NET Framework. Al especificar los archivos de texto específicamente, el `OpenTextFileReader` ayuda al usuario a comprender qué secuencia usar.

Estas instrucciones no impiden los principios de diseño generales de las bibliotecas de clases. En su lugar, son recomendaciones que están optimizadas para los desarrolladores que usan Visual Basic y el espacio de nombres `My`. Para obtener los principios de diseño generales para crear bibliotecas de clases, vea [directrices de diseño de marco](../../../standard/design-guidelines/index.md).

## <a name="packaging-and-deploying-extensions"></a>Empaquetar e implementar extensiones

Puede incluir `My` extensiones de espacio de nombres en una plantilla de proyecto de Visual Studio, o puede empaquetar las extensiones e implementarlas como una plantilla de elementos de Visual Studio. Al empaquetar las extensiones de espacio de nombres de `My` como una plantilla de elementos de Visual Studio, puede aprovechar las capacidades adicionales que proporciona Visual Basic. Estas funcionalidades permiten incluir una extensión cuando un proyecto hace referencia a un ensamblado determinado, o bien permitir que los usuarios agreguen explícitamente la extensión de espacio de nombres `My` mediante la página **mis extensiones** del diseñador de proyectos de Visual Basic.

Para obtener más información sobre cómo implementar `My` extensiones de espacio de nombres, consulte [empaquetar e implementar extensiones My personalizadas](packaging-and-deploying-custom-my-extensions.md).

## <a name="see-also"></a>Vea también

- [Empaquetado e implementación de extensiones de My personalizadas](packaging-and-deploying-custom-my-extensions.md)
- [Extensión del modelo de la aplicación de Visual Basic](extending-the-visual-basic-application-model.md)
- [Personalización de los objetos que están disponibles en My](customizing-which-objects-are-available-in-my.md)
- [Página Mis extensiones del Diseñador de proyectos](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
- [Página de aplicación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Partial](../../language-reference/modifiers/partial.md)
