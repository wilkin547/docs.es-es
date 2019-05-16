---
title: Miembros
description: Obtenga información acerca de los miembros de objeto en el F# lenguaje de programación.
ms.date: 05/16/2016
ms.openlocfilehash: 0da704b637a9421aa150aa8d8de504bec858e252
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645154"
---
# <a name="members"></a>Miembros

En esta sección se describen los miembros de los tipos de objeto de F#.

## <a name="remarks"></a>Comentarios

Los *miembros* son características que forman parte de una definición de tipo y se declaran con la palabra clave `member`. Los tipos de objeto de F#, como los registros, clases, uniones discriminadas, interfaces y estructuras, admiten miembros. Para más información, vea [Registros](../records.md), [Clases](../classes.md), [Uniones discriminadas](../discriminated-Unions.md), [Interfaces](../interfaces.md) y [Estructuras](../structures.md).

Normalmente, los miembros componen la interfaz pública de un tipo, por lo que son públicos a menos que se especifique lo contrario. Los miembros también pueden declararse como privados o internos. Para más información, vea [Access Control](../access-Control.md) (Control de acceso). También se pueden usar firmas de tipos para exponer o no determinados miembros de un tipo. Para más información, vea [Signatures](../signatures.md) (Firmas).

Los campos privados y los enlaces `do`, que se usan únicamente con las clases, no son miembros auténticos ya que nunca forman parte de la interfaz pública de un tipo y no se declaran con la palabra clave `member`, pero también se describen en esta sección.

## <a name="related-topics"></a>Temas relacionados

|Tema|Descripción|
|-----|-----------|
|[`let` Bindings in Classes](let-bindings-in-classes.md) (Enlaces `let` en clases)|Describe la definición de campos privados y funciones en las clases.|
|[`do` Bindings in Classes](do-bindings-in-classes.md) (Enlaces `do` en clases)|Describe la especificación de código de inicialización de objetos.|
|[Propiedades](properties.md)|Describe los miembros de propiedad de las clases y otros tipos.|
|[Propiedades indexadas](indexed-properties.md)|Describe propiedades similares a matrices de las clases y otros tipos.|
|[Métodos](methods.md)|Describe funciones que son miembros de un tipo.|
|[Constructores](constructors.md)|Describe funciones especiales que inicializan objetos de un tipo.|
|[Sobrecarga de operadores](../operator-overloading.md)|Describe la definición de operadores personalizados para tipos.|
|[Eventos](events.md)|Describe la definición y la compatibilidad con el control de eventos en F#.|
|[Campos explícitos: `val`Palabra clave](explicit-fields-the-val-keyword.md)|Describe la definición de campos no inicializados en un tipo.|
