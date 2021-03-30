---
title: Actualización segura de las interfaces mediante el uso de métodos de interfaz predeterminada en C#
description: En este tutorial avanzado se describe cómo agregar de forma segura nuevas capacidades a las definiciones de la interfaz existente sin que ello interrumpa todas las clases y estructuras que implementan esa interfaz.
ms.date: 05/06/2019
ms.technlogy: csharp-advanced-concepts
ms.custom: mvc
ms.openlocfilehash: 43af25cee765ba18543b0c7bfe0069542a90e0e5
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104878945"
---
# <a name="tutorial-update-interfaces-with-default-interface-methods-in-c-80"></a>Tutorial: Actualización de las interfaces mediante el uso de métodos de interfaz predeterminados en C# 8.0

A partir de C# 8.0 en .NET Core 3.0, puede definir una implementación cuando declare un miembro de una interfaz. El escenario más común es agregar de forma segura a miembros a una interfaz ya publicada y utilizada por clientes incontables.

En este tutorial aprenderá lo siguiente:

> [!div class="checklist"]
>
> * Extender interfaces de forma segura mediante la adición de métodos con implementaciones.
> * Crear implementaciones con parámetros para proporcionar mayor flexibilidad.
> * Permitir que los implementadores proporcionen una implementación más específica en forma de una invalidación.

## <a name="prerequisites"></a>Requisitos previos

Deberá configurar la máquina para ejecutar .NET Core, incluido el compilador de C# 8.0. El compilador de C# 8.0 está disponible a partir de la [versión 16.3 de Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o del [SDK de .NET Core 3.0](https://dotnet.microsoft.com/download).

## <a name="scenario-overview"></a>Información general del escenario

Este tutorial comienza con la versión 1 de una biblioteca de relaciones con clientes. Puede obtener la aplicación de inicio en nuestro [repositorio de ejemplo en GitHub](https://github.com/dotnet/samples/tree/main/csharp/tutorials/default-interface-members-versions/starter/customer-relationship). La empresa que creó esta biblioteca se dirigía a los clientes con aplicaciones existentes para adoptar sus bibliotecas. Proporcionan definiciones de una interfaz mínima para que la implemente los usuarios de su biblioteca. Esta es la definición de interfaz para un cliente:

[!code-csharp[InitialCustomerInterface](~/samples/snippets/csharp/tutorials/default-interface-members-versions/starter/customer-relationship/ICustomer.cs?name=SnippetICustomerVersion1)]

Definieron una segunda interfaz que representa un pedido:

[!code-csharp[InitialOrderInterface](~/samples/snippets/csharp/tutorials/default-interface-members-versions/starter/customer-relationship/IOrder.cs?name=SnippetIorderVersion1)]

En esas interfaces, el equipo pudo generar una biblioteca para sus usuarios con el fin de crear una mejor experiencia para los clientes. Su objetivo era crear una relación más estrecha con los clientes existentes y mejorar sus relaciones con los clientes nuevos.

Ahora, es momento de actualizar la biblioteca para la próxima versión. Una de las características solicitadas permite un descuento por fidelidad para los clientes que tienen muchos pedidos. Este nuevo descuento por fidelidad se aplica cada vez que un cliente realiza un pedido. El descuento específico es una propiedad de cada cliente individual. Cada implementación de `ICustomer` puede establecer reglas diferentes para el descuento por fidelidad.

La forma más natural para agregar esta funcionalidad es mejorar la interfaz `ICustomer` con un método para aplicar los descuentos por fidelización. Esta sugerencia de diseño es motivo de preocupación entre los desarrolladores experimentados: "Las interfaces son inmutables una vez que se han publicado. ¡Es un cambio importante!" C# 8.0 agrega *las implementaciones de interfaz predeterminadas* para actualizar las interfaces. Los autores de bibliotecas pueden agregar a nuevos miembros a la interfaz y proporcionar una implementación predeterminada para esos miembros.

Las implementaciones de interfaces predeterminadas permiten a los desarrolladores actualizar una interfaz mientras siguen permitiendo que los implementadores invaliden esa implementación. Los usuarios de la biblioteca pueden aceptar la implementación predeterminada como un cambio sin importancia. Si sus reglas de negocios son diferentes, se puede invalidar.

## <a name="upgrade-with-default-interface-methods"></a>Actualización con los métodos de interfaz predeterminados

El equipo estuvo de acuerdo en la más probable implementación predeterminada: un descuento por fidelidad para los clientes.

La actualización debe proporcionar la funcionalidad para establecer dos propiedades: el número de pedidos necesario para poder recibir el descuento y el porcentaje del descuento. Esto lo convierte en un escenario perfecto para los métodos de interfaz predeterminados. Puede agregar un método a la interfaz de `ICustomer` y proporcionar la implementación más probable. Todas las implementaciones existentes y nuevas pueden usar la implementación predeterminada o proporcionar una propia.

En primer lugar, agregue el nuevo método a la interfaz, incluido su cuerpo:

[!code-csharp[InitialOrderInterface](~/samples/snippets/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/ICustomer.cs?name=SnippetLoyaltyDiscountVersionOne)]

El autor de la biblioteca escribió una primera prueba para comprobar la implementación:

[!code-csharp[TestDefaultImplementation](~/samples/snippets/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/Program.cs?name=SnippetTestDefaultImplementation)]

Tenga en cuenta la siguiente parte de la prueba:

[!code-csharp[TestDefaultImplementation](~/samples/snippets/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/Program.cs?name=SnippetHighlightCast)]

La conversión de `SampleCustomer` a `ICustomer` es necesaria. La clase `SampleCustomer` no necesita proporcionar una implementación para `ComputeLoyaltyDiscount`. La interfaz `ICustomer` la proporciona. Sin embargo, la clase `SampleCustomer` no hereda miembros de sus interfaces. Esa no ha cambiado. Para poder llamar a cualquier método declarado e implementado en la interfaz, la variable debe ser del tipo de la interfaz: `ICustomer` en este ejemplo.

## <a name="provide-parameterization"></a>Proporcionar parametrización

Ese es un buen inicio. Pero la implementación predeterminada es demasiado restrictiva. Muchos consumidores de este sistema pueden elegir diferentes umbrales para el número de compras, una longitud diferente de la pertenencia o un porcentaje diferente del descuento. Puede proporcionar una mejor experiencia de actualización para más clientes proporcionando una manera de establecer esos parámetros. Vamos a agregar un método estático que establezca esos tres parámetros controlando la implementación predeterminada:

[!code-csharp[VersionTwoImplementation](~/samples/snippets/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/ICustomer.cs?name=SnippetLoyaltyDiscountVersionTwo)]

Hay muchas funcionalidades nuevas de lenguaje que se muestran en este pequeño fragmento de código. Las interfaces ahora pueden incluir miembros estáticos, incluidos campos y métodos. También están habilitados diferentes modificadores de acceso. Los campos adicionales son privados, el nuevo método es público. Todos los modificadores están permitidos en los miembros de la interfaz.

Las aplicaciones que usan la fórmula general para calcular el descuento por fidelidad, pero diferentes parámetros, no necesitan proporcionar una implementación personalizada: pueden establecer los argumentos a través de un método estático. Por ejemplo, el siguiente código establece una "apreciación de cliente" que recompensa a cualquier cliente con más de una pertenencia al mes:

[!code-csharp[SetLoyaltyThresholds](~/samples/snippets/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/Program.cs?name=SnippetSetLoyaltyThresholds)]

## <a name="extend-the-default-implementation"></a>Extender la implementación predeterminada

El código que ha agregado hasta ahora ha proporcionado una implementación adecuada para los escenarios donde los usuarios quieren algo similar a la implementación predeterminada, o para proporcionar un conjunto de reglas no relacionado. Para una característica final, vamos a refactorizar el código un poco para habilitar los escenarios donde es posible que los usuarios deseen crear en la implementación predeterminada.

Considere una startup que desea captar nuevos clientes. Ofrecen un descuento del 50 % en el primer pedido de un cliente nuevo. De lo contrario, los clientes existentes obtienen el descuento estándar. El autor de la biblioteca necesita mover la implementación predeterminada a un método `protected static` para que cualquier clase que implemente esta interfaz pueda reutilizar el código en su implementación. La implementación predeterminada del miembro de la interfaz llama a este método compartido así:

[!code-csharp[VersionTwoImplementation](~/samples/snippets/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/ICustomer.cs?name=SnippetFinalVersion)]

En una implementación de una clase que implementa esta interfaz, la invalidación puede llamar al método auxiliar estático y ampliar esa lógica para proporcionar el descuento de "cliente nuevo":

[!code-csharp[VersionTwoImplementation](~/samples/snippets/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/SampleCustomer.cs?name=SnippetOverrideAndExtend)]

Puede ver todo el código terminado en nuestro [repositorio de ejemplos en GitHub](https://github.com/dotnet/samples/tree/main/csharp/tutorials/default-interface-members-versions/finished/customer-relationship). Puede obtener la aplicación de inicio en nuestro [repositorio de ejemplo en GitHub](https://github.com/dotnet/samples/tree/main/csharp/tutorials/default-interface-members-versions/starter/customer-relationship).

Estas nuevas características significan que las interfaces se pueden actualizar de forma segura cuando hay una implementación predeterminada razonable para esos nuevos miembros. Diseñe cuidadosamente las interfaces para expresar ideas funcionales únicas que puedan implementarse con varias clases. Esto facilita la actualización de esas definiciones de interfaz cuando se descubren nuevos requisitos para esa misma idea funcional.
