---
title: Instrucciones de diseño de tipos
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
ms.openlocfilehash: a20744f76433ff12456967e4d41d9a13b6f5d46c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677536"
---
# <a name="type-design-guidelines"></a>Instrucciones de diseño de tipos

Desde la perspectiva de CLR, solo hay dos categorías de tipos: tipos de referencia y tipos de valor, pero para la finalidad de un debate sobre el diseño del marco, dividimos los tipos en grupos más lógicos, cada uno con sus propias reglas de diseño específicas.

 Las clases son el caso general de los tipos de referencia. Componen la mayor parte de los tipos en la mayoría de los marcos de trabajo. Las clases deben tener su popularidad al amplio conjunto de características orientadas a objetos que admiten y a su aplicabilidad general. Las clases base y las clases abstractas son grupos lógicos especiales relacionados con la extensibilidad.

 Las interfaces son tipos que pueden ser implementados por tipos de referencia y tipos de valor. Por tanto, pueden actuar como raíces de jerarquías polimórficas de tipos de referencia y tipos de valor. Además, las interfaces se pueden usar para simular la herencia múltiple, que no es compatible de forma nativa con CLR.

 Los Structs son el caso general de los tipos de valor y se deben reservar para tipos pequeños y simples, similares a los primitivos del lenguaje.

 Las enumeraciones son un caso especial de tipos de valor que se usan para definir breves conjuntos de valores, como los días de la semana, los colores de la consola, etc.

 Las clases estáticas son tipos diseñados para ser contenedores de miembros estáticos. Normalmente se utilizan para proporcionar accesos directos a otras operaciones.

 Los delegados, las excepciones, los atributos, las matrices y las colecciones son casos especiales de tipos de referencia destinados a usos específicos, y las instrucciones para su diseño y uso se tratan en otra parte de este libro.

 ✔️ asegurarse de que cada tipo es un conjunto bien definido de miembros relacionados, no solo una colección aleatoria de funcionalidad no relacionada.

## <a name="in-this-section"></a>En esta sección

 [Elección entre clase y struct clase](choosing-between-class-and-struct.md) [abstracta diseño](abstract-class.md) de clases [estáticas](static-class.md) [diseño](interface.md) de clases [estructura](struct.md) [Enum Design](enum.md) de diseño de clase [tipo anidado](nested-types.md) *partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Directrices de diseño de marco](index.md)
