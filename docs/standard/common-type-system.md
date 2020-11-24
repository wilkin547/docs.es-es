---
title: Common Type System y Common Language Specification
description: Obtenga información sobre cómo Common Type System (CTS) y Common Language Specification (CLS) hacen posible que .NET admita varios lenguajes.
ms.date: 06/20/2016
ms.assetid: 3b1f5725-ac94-4f17-8e5f-244442438a4d
ms.openlocfilehash: e60205450e2f156407deb7be6b9c497d090b6f7b
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822885"
---
# <a name="common-type-system--common-language-specification"></a>Common Type System y Common Language Specification

De nuevo, dos términos que se usan libremente en el mundo de .NET, en realidad, son cruciales para entender cómo permite una implementación de .NET el desarrollo de varios lenguajes y para entender cómo funciona.

## <a name="common-type-system"></a>Sistema de tipos comunes

Para comenzar desde el principio, recuerde que una implementación de .NET es _independiente del lenguaje_. Esto no solo significa que un programador pueda escribir su código en cualquier lenguaje que se pueda compilar en IL, sino también que tiene que poder interactuar con código escrito en otros lenguajes que se pueden usar en una implementación de .NET.

Para hacer esto de forma transparente, debe haber una forma común de describir todos los tipos compatibles. De esto se encarga Common Type System (CTS). Se ha creado para realizar varias acciones:

* Establecer un marco para la ejecución de varios lenguajes.
* Proporcionar un modelo orientado a objetos para admitir la implementación de varios lenguajes en una implementación de .NET.
* Definir un conjunto de reglas que deben seguir todos los lenguajes al trabajar con tipos.
* Proporcionar una biblioteca que contenga los tipos de datos primitivos que se emplean en el desarrollo de aplicaciones (por ejemplo, `Boolean`, `Byte`, `Char`, etc.).

CTS define dos tipos principales que deben ser compatibles: tipos de referencia y valor. Sus nombres indican sus definiciones.

Los objetos de los tipos de referencia se representan mediante una referencia al valor real del objeto; aquí, una referencia es similar a un puntero en C/C++. Simplemente, hace referencia a una ubicación de memoria donde están los valores de los objetos. Esto tiene un impacto profundo sobre cómo se usan estos tipos. Si asigna un tipo de referencia a una variable y después pasa esa variable en un método, por ejemplo, se reflejarán los cambios del objeto en el objeto principal; no hay ninguna copia.

Los tipos de valor son lo opuesto, donde los objetos se representan mediante sus valores. Si asigna un tipo de valor a una variable, está copiando un valor del objeto.

CTS define varias categorías de tipos, cada una con su semántica y uso específicos:

* Clases
* Estructuras
* Enumeraciones
* Interfaces
* Delegados

CTS también define todas las demás propiedades de los tipos, como modificadores de acceso, cuáles son los miembros de tipo válidos, cómo funcionan la herencia y la sobrecarga, etc. Desafortunadamente, profundizar sobre cualquiera de ellas queda fuera del ámbito de un artículo de introducción como este, pero puede consultar la sección [Más recursos](#more-resources) al final para obtener vínculos a contenido más detallado que trata estos temas.

## <a name="common-language-specification"></a>Common Language Specification

Para habilitar escenarios de interoperabilidad completa, todos los objetos que se creen en el código deben basarse en algunas similitudes en los lenguajes que los usan (son sus _llamadores_). Puesto que hay numerosos lenguajes diferentes, .NET ha especificado las similitudes en lo que se denomina **Common Language Specification** (CLS). CLS define un conjunto de características que son necesarias para muchas aplicaciones comunes. También proporciona una especie de receta para cualquier lenguaje que se implementa sobre .NET sobre qué necesita para ser compatible.

CLS es un subconjunto de CTS. Esto significa que todas las reglas de CTS se aplican también a CLS, a menos que las reglas de CLS sean más estrictas. Si un componente se compila solo con las reglas de CLS, es decir, expone solo las características de CLS en la API, se dice que es **conforme a CLS**. Por ejemplo, las `<framework-librares>` son conformes a CLS precisamente porque tienen que funcionar en todos los lenguajes que se admiten en .NET.

Puede consultar los documentos de la sección [Más recursos](#more-resources) a continuación para obtener una información general de todas las características de CLS.

## <a name="more-resources"></a>Más recursos

* [Sistema de tipos comunes](./base-types/common-type-system.md)
* [Common Language Specification](language-independence-and-language-independent-components.md)
