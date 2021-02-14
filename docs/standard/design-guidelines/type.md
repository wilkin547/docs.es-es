---
description: 'Más información acerca de: Instrucciones de diseño de tipos'
title: Instrucciones de diseño de tipos
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
ms.openlocfilehash: d2c193d41dda118558cc5e7541f7e2dfbaf1a369
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641842"
---
# <a name="type-design-guidelines"></a>Instrucciones de diseño de tipos

Desde la perspectiva de CLR, solo hay dos categorías de tipos (tipos de referencia y tipos de valor) pero para la finalidad de un debate sobre el diseño del marco, dividimos los tipos en grupos más lógicos, cada uno con sus propias reglas de diseño específicas.

 Las clases son el caso general de los tipos de referencia. Componen la mayor parte de los tipos en la mayoría de los marcos. Las clases deben su popularidad al amplio conjunto de características orientadas a objetos que admiten y a su aplicabilidad general. Las clases base y las clases abstractas son grupos lógicos especiales relacionados con la extensibilidad.

 Las interfaces son tipos que tanto los tipos de referencia como los tipos de valor pueden implementar. Por tanto, pueden actuar como raíces de jerarquías polimórficas de tipos de referencia y tipos de valor. Además, las interfaces se pueden usar para simular la herencia múltiple, que no es compatible de forma nativa con CLR.

 Los structs son el caso general de los tipos de valor y se deben reservar para tipos pequeños y simples, similares a los primitivos del lenguaje.

 Las enumeraciones son un caso especial de tipos de valor que se usan para definir breves conjuntos de valores, como los días de la semana, los colores de la consola, etc.

 Las clases estáticas son tipos diseñados para ser contenedores de miembros estáticos. Normalmente se utilizan para proporcionar accesos directos a otras operaciones.

 Los delegados, las excepciones, los atributos, las matrices y las colecciones son casos especiales de tipos de referencia destinados a usos específicos, y las instrucciones para su diseño y uso se tratan en otra parte de este libro.

 ✔️ DEBE asegurarse de que cada tipo es un conjunto bien definido de miembros relacionados, no solo una colección aleatoria de funcionalidad no relacionada.

## <a name="in-this-section"></a>En esta sección

 [Elegir entre clases y structs](choosing-between-class-and-struct.md) [Diseño de clases abstractas](abstract-class.md) [Diseño de clases estáticas](static-class.md) [Diseño de interfaces](interface.md) [Diseño de structs](struct.md) [Diseño de enumeraciones](enum.md) [Tipos anidados](nested-types.md) *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](index.md)
