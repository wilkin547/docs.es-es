---
title: Extensión del espacio de nombres de My
ms.date: 07/20/2015
f1_keywords:
- vb.AddingMyExtensions
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
ms.openlocfilehash: 2a7b0b84061fccd9a333a68e4a19477bd19ca4ff
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330309"
---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Extensión del espacio de nombres `My` en Visual Basic

El espacio de nombres `My` de Visual Basic expone propiedades y métodos que le permiten aprovechar fácilmente la eficacia de .NET Framework. El espacio de nombres `My` simplifica problemas comunes de programación, lo que a menudo reduce una tarea compleja a una sola línea de código. Además, el espacio de nombres `My` es totalmente extensible, por lo que puede personalizar el comportamiento de `My` y agregar nuevos servicios a su jerarquía para adaptarse a las necesidades específicas de la aplicación. En este tema se explica cómo personalizar los miembros existentes del espacio de nombres `My` y cómo agregar clases personalizadas propias al espacio de nombres `My`.

## <a name="customizing-existing-my-namespace-members"></a>Personalización de los miembros del espacio de nombres `My` existentes

El espacio de nombres `My` de Visual Basic expone información de uso frecuente sobre la aplicación, el equipo, etc. Para obtener una lista completa de los objetos del espacio de nombres `My`, vea [Referencia de My](../../language-reference/keywords/my-reference.md). Es posible que tenga que personalizar los miembros existentes del espacio de nombres `My` de modo que se ajusten mejor a las necesidades de la aplicación. Cualquier propiedad de un objeto en el espacio de nombres `My` que no sea de solo lectura se puede establecer en un valor personalizado.

Por ejemplo, imagine que habitualmente usa el objeto `My.User` para acceder al contexto de seguridad actual para el usuario que ejecuta la aplicación. Pero en la empresa se utiliza un objeto de usuario personalizado para exponer información y funciones adicionales para los usuarios. En este escenario, puede reemplazar el valor predeterminado de la propiedad `My.User.CurrentPrincipal` por una instancia de un objeto de entidad de seguridad personalizado propio, como se muestra en el ejemplo siguiente:

[!code-vb[VbVbcnExtendingMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#1)]

Al establecer la propiedad `CurrentPrincipal` en el objeto `My.User`, cambia la identidad bajo la que se ejecuta la aplicación. El objeto `My.User`, a su vez, devuelve información sobre el usuario recién especificado.
  
## <a name="adding-members-to-my-objects"></a>Adición de miembros a objetos `My`

Los tipos devueltos de `My.Application` y `My.Computer` se definen como clases `Partial`. Por tanto, puede extender los objetos `My.Application` y `My.Computer` si crea una clase `Partial` denominada `MyApplication` o `MyComputer`. La clase no puede ser una clase `Private`. Si especifica la clase como parte del espacio de nombres `My`, puede agregar propiedades y métodos que se incluirán con los objetos `My.Application` o `My.Computer`.

En el ejemplo siguiente se agrega una propiedad denominada `DnsServerIPAddresses` al objeto `My.Computer`:

[!code-vb[VbVbcnExtendingMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class2.vb#2)]

## <a name="adding-custom-objects-to-the-my-namespace"></a>Adición de objetos personalizados al espacio de nombres `My`

Aunque el espacio de nombres `My` proporciona soluciones para muchas tareas de programación comunes, puede encontrar algunas que no se aborden en el espacio de nombres `My`. Por ejemplo, es posible que la aplicación acceda a servicios de directorio personalizados para los datos de usuario, o bien que use ensamblados que no se instalen de forma predeterminada con Visual Basic. Puede extender el espacio de nombres `My` a fin de incluir soluciones personalizadas para tareas comunes específicas del entorno. El espacio de nombres `My` se puede ampliar fácilmente para agregar nuevos miembros a fin de satisfacer las necesidades crecientes de las aplicaciones. Además, puede implementar las extensiones del espacio de nombres `My` para otros desarrolladores como una plantilla de Visual Basic.
  
### <a name="adding-members-to-the-my-namespace"></a>Adición de miembros al espacio de nombres `My`

Como `My` es un espacio de nombres como cualquier otro, puede agregarle propiedades de nivel superior si simplemente agrega un módulo y especifica un `Namespace` con el valor `My`. Anote el módulo con el atributo `HideModuleName`, como se muestra en el ejemplo siguiente. El atributo `HideModuleName` garantiza que IntelliSense no mostrará el nombre del módulo cuando muestre los miembros del espacio de nombres `My`.

[!code-vb[VbVbcnExtendingMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#3)]

Para agregar miembros al espacio de nombres `My`, agregue las propiedades al módulo según sea necesario. Para cada propiedad agregada al espacio de nombres `My`, agregue un campo privado de tipo `ThreadSafeObjectProvider(Of T)`, donde el tipo es el tipo devuelto por la propiedad personalizada. Este campo se usa para crear instancias de objetos seguros para subprocesos que la propiedad devolverá mediante la llamada al método `GetInstance`. Como resultado, cada subproceso que accede a la propiedad extendida recibe su propia instancia del tipo devuelto. En el ejemplo siguiente se agrega una propiedad denominada `SampleExtension` de tipo `SampleExtension` al espacio de nombres `My`:

[!code-vb[VbVbcnExtendingMy#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#4)]

## <a name="adding-events-to-custom-my-objects"></a>Adición de eventos a objetos `My` personalizados

Puede usar el objeto `My.Application` para exponer eventos para los objetos `My` personalizados si extiende la clase parcial `MyApplication` en el espacio de nombres `My`. En el caso de los proyectos basados en Windows, puede hacer doble clic en el nodo **Mi proyecto** del proyecto en el **Explorador de soluciones**. En el **Diseñador de proyectos** de Visual Basic, haga clic en la pestaña **Aplicación** y después en el botón **Ver eventos de aplicaciones**. Se creará un archivo con el nombre *ApplicationEvents.vb*. Contiene el código siguiente para extender la clase `MyApplication`:

[!code-vb[VbVbcnExtendingMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#5)]

Puede agregar controladores de eventos para los objetos `My` personalizados si agrega controladores de eventos personalizados a la clase `MyApplication`. Los eventos personalizados permiten agregar código que se ejecutará cuando se agregue o se quite un controlador de eventos, o cuando se genere el evento. Tenga en cuenta que el código de `AddHandler` para un evento personalizado solo se ejecuta si un usuario agrega el código para controlar el evento. Por ejemplo, imagine que el objeto `SampleExtension` de la sección anterior tiene un evento `Load` para el que quiere agregar un controlador de eventos personalizado. En el ejemplo de código siguiente se muestra un controlador de eventos personalizado denominado `SampleExtensionLoad` que se invocará cuando se produzca el evento `My.SampleExtension.Load`. Cuando se agrega código para controlar el nuevo evento `My.SampleExtensionLoad`, se ejecuta el elemento `AddHandler` de este código de evento personalizado. El método `MyApplication_SampleExtensionLoad` se incluye en el ejemplo de código para mostrar un ejemplo de un controlador de eventos que controla el evento `My.SampleExtensionLoad`. Tenga en cuenta que el evento `SampleExtensionLoad` estará disponible al seleccionar la opción **Mis eventos de aplicación** en la lista desplegable de la izquierda situada encima del editor de código al modificar el archivo *ApplicationEvents.vb*.

[!code-vb[VbVbcnExtendingMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#6)]

## <a name="design-guidelines"></a>Directrices de diseño

Al desarrollar extensiones para el espacio de nombres `My`, use las instrucciones para ayudar a minimizar los costos de mantenimiento de los componentes de la extensión:

- **Incluya solo la lógica de la extensión.** La lógica incluida en la extensión del espacio de nombres `My` debe incluir solo el código necesario para exponer la funcionalidad necesaria en el espacio de nombres `My`. Como la extensión residirá en los proyectos de usuario como código fuente, la actualización del componente de extensión incurrirá en un alto costo de mantenimiento y se debe evitar si es posible.
- **Minimizar las suposiciones sobre el proyecto.** Al crear las extensiones del espacio de nombres `My`, no asuma un conjunto de referencias, importaciones de nivel de proyecto o configuraciones de compilador específicas (por ejemplo, `Option Strict` desactivada). En su lugar, minimice las dependencias y use nombres completos para todas las referencias de tipos mediante la palabra clave `Global`. Además, asegúrese de que la extensión se compila con `Option Strict` activado para minimizar los errores.
- **Aísle el código de la extensión.** Si coloca el código en un único archivo, la extensión se podrá implementar fácilmente como una plantilla de elemento de Visual Studio. Para obtener más información, vea "Empaquetado e implementación de extensiones", más adelante en este tema. Si coloca todo el código de la extensión del espacio de nombres `My` en un solo archivo o en una carpeta independiente de un proyecto también ayudará a los usuarios a encontrar la extensión del espacio de nombres `My`.

## <a name="designing-class-libraries-for-my"></a>Diseño de bibliotecas de clases para `My`

Como sucede con la mayoría de los modelos de objetos, algunos patrones de diseño funcionan bien en el espacio de nombres `My` y otros no. Al diseñar una extensión para el espacio de nombres `My`, tenga en cuenta los principios siguientes:

- **Métodos sin estado.** Los métodos del espacio de nombres `My` deben proporcionar una solución completa a una tarea específica. Asegúrese de que los valores de parámetro que se pasan al método proporcionan toda la entrada necesaria para completar la tarea en cuestión. Evite crear métodos que se basen en un estado anterior, como conexiones abiertas a recursos.
- **Instancias globales.** El único estado que se mantiene en el espacio de nombres `My` es global para el proyecto. Por ejemplo, `My.Application.Info` encapsula el estado que se comparte en toda la aplicación.
- **Tipos de parámetros simples.** Evite tipos de parámetro complejos para que todo sea más sencillo. En su lugar, cree métodos que no tomen parámetros como entrada o que tomen tipos de entrada simples como cadenas, tipos primitivos, etc.
- **Factory Method.** La creación de instancias de algunos tipos es inevitablemente compleja. Proporcionar Factory Method como extensiones para el espacio de nombres `My` permite detectar y consumir más fácilmente los tipos que se encuentran en esta categoría. Un ejemplo de Factory Method que funciona bien es `My.Computer.FileSystem.OpenTextFileReader`. Hay varios tipos de secuencias disponibles en .NET Framework. Al especificar los archivos de texto de forma concreta, `OpenTextFileReader` ayuda al usuario a comprender qué secuencia usar.

Estas instrucciones no excluyen los principios de diseño generales de las bibliotecas de clases. Por el contrario, son recomendaciones optimizadas para los desarrolladores que usan Visual Basic y el espacio de nombres `My`. Para obtener los principios de diseño generales de creación de bibliotecas de clases, vea [Instrucciones de diseño de .NET Framework](../../../standard/design-guidelines/index.md).

## <a name="packaging-and-deploying-extensions"></a>Empaquetado e implementación de extensiones

Puede incluir extensiones del espacio de nombres `My` en una plantilla de proyecto de Visual Studio, o bien puede empaquetar las extensiones e implementarlas como una plantilla de elemento de Visual Studio. Al empaquetar las extensiones del espacio de nombres `My` como una plantilla de elemento de Visual Studio, puede aprovechar las funciones adicionales que proporciona Visual Basic. Estas funciones permiten incluir una extensión cuando un proyecto hace referencia a un ensamblado concreto, o bien que los usuarios agreguen de forma explícita la extensión del espacio de nombres `My` mediante la página  **Extensiones My** del Diseñador de proyectos de Visual Basic.

Para obtener más información sobre cómo implementar extensiones de espacio de nombres `My`, vea [Empaquetado e implementación de extensiones My personalizadas](packaging-and-deploying-custom-my-extensions.md).

## <a name="see-also"></a>Vea también

- [Empaquetado e implementación de extensiones de My personalizadas](packaging-and-deploying-custom-my-extensions.md)
- [Extensión del modelo de la aplicación de Visual Basic](extending-the-visual-basic-application-model.md)
- [Personalización de los objetos que están disponibles en My](customizing-which-objects-are-available-in-my.md)
- [Página Mis extensiones del Diseñador de proyectos](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
- [Página de aplicación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Partial](../../language-reference/modifiers/partial.md)
