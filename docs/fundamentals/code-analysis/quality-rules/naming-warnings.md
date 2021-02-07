---
title: Reglas de nomenclatura (análisis de código)
description: Obtenga información sobre las reglas de nomenclatura de análisis de código.
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.namingrules
helpviewer_keywords:
- managed code analysis rules, naming rules
- naming rules
- rules, naming
author: gewarren
ms.author: gewarren
ms.openlocfilehash: 57524fbff364fd03a90b90a0900bd17e9c8a9248
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732324"
---
# <a name="naming-rules"></a>Reglas de nomenclatura

Las reglas de nomenclatura admiten el cumplimiento [de las convenciones de nomenclatura de las instrucciones de diseño de .net](../../../standard/design-guidelines/naming-guidelines.md).

## <a name="in-this-section"></a>En esta sección

|Regla|Descripción|
|----------|-----------------|
|[CA1700: No nombrar valores de enumeración como 'Reserved'](ca1700.md)|Esta regla supone que un miembro de la enumeración con un nombre que contiene la palabra "reserved" no se utiliza actualmente pero hace de marcador de posición para que se pueda quitar o cambiar el nombre en una versión posterior. Quitar o cambiar el nombre de un miembro es un cambio importante.|
|[CA1707: Los identificadores no deben contener caracteres de subrayado](ca1707.md)|Por convención, los nombres del identificador no contienen el carácter de subrayado (_). Esta regla comprueba espacios de nombres, tipos, miembros y parámetros.|
|[CA1708: Los identificadores se deben diferenciar en algo más que en el uso de mayúsculas y minúsculas](ca1708.md)|Los identificadores de los espacios de nombres, miembros y parámetros no puede distinguirse sólo por mayúsculas o minúsculas porque los lenguajes que tienen como destino el Common Language Runtime no necesitan distinguir entre mayúsculas y minúsculas.|
|[CA1710: Los identificadores deben tener un sufijo correcto](ca1710.md)|Por Convención, los nombres de tipos que extienden determinados tipos base o que implementan determinadas interfaces, o tipos derivados de estos tipos, tienen un sufijo que está asociado con el tipo base o la interfaz.|
|[CA1711: Los identificadores no deben tener un sufijo incorrecto](ca1711.md)|Por convención, los nombres de tipos que extienden determinados tipos base o que implementan algunas interfaces, o tipos derivados de estos tipos, deben terminar con unos sufijos reservados específicos. Otros nombres de tipo no deben utilizar estos sufijos reservados.|
|[CA1712: No utilizar prefijos en valores de enumeración con el nombre del tipo](ca1712.md)|Los nombres de los miembros de enumeración no tienen como prefijo el nombre de tipo porque se espera que las herramientas de Desarrollo proporcionen información de tipo.|
|[CA1713: Los eventos no deben tener prefijos antes ni después](ca1713.md)|El nombre de un evento empieza por "Before" o "After". Para nombrar los eventos relacionados que se provocan en una secuencia específica, utilice el tiempo presente o pasado para indicar la posición relativa en la secuencia de acciones.|
|[CA1714: Las enumeraciones Flags deben tener nombres en plural](ca1714.md)|Una enumeración pública tiene el atributo System. FlagsAttribute y su nombre no termina en "s". Los tipos marcados con FlagsAttribute tienen nombres que son plurales porque el atributo indica que se puede especificar más de un valor.|
|[CA1715: Los identificadores deben tener el prefijo correcto](ca1715.md)|El nombre de una interfaz visible externamente no empieza con una "I" mayúscula.  El nombre de un parámetro de tipo genérico en un tipo o método visible externamente no empieza con una "T" mayúscula.|
|[CA1716: Los identificadores no deben coincidir con palabras clave](ca1716.md)|Un nombre de espacio de nombres o un nombre de tipo coinciden con una palabra clave reservada en un lenguaje de programación. Los identificadores para los espacios de nombres y tipos no deberían coincidir con palabras clave definidas por los lenguajes que tienen como destino el Common Language Runtime.|
|[CA1717: Solo las enumeraciones FlagsAttribute deben tener nombres en plural](ca1717.md)|Las convenciones de nomenclatura establecen que un nombre en plural para una enumeración indica que se pueden especificar varios valores de enumeración al mismo tiempo.|
|[CA1720: Los identificadores no deben contener nombres de tipo](ca1720.md)|El nombre de un parámetro en un miembro visible externamente contiene un nombre de tipo de datos o el nombre de un miembro visible externamente contiene un nombre de tipo de datos específico del lenguaje.|
|[CA1721: Los nombres de propiedades no deben coincidir con los métodos get](ca1721.md)|El nombre de un miembro público o protegido empieza por "Get" y en cualquier otro caso coincide con el nombre de una propiedad pública o protegida. Las propiedades y métodos "Get" deberían tener nombres que distingan claramente su función.|
|[CA1724: Los nombres de tipo no deben coincidir con los espacios de nombres](ca1724.md)|Los nombres de tipo no deben coincidir con los nombres de los espacios de nombres de .NET. Una infracción de esta regla puede reducir la facilidad de uso de la biblioteca.|
|[CA1725: Los nombres de parámetro deben coincidir con la declaración base](ca1725.md)|El uso del mismo nombre para un parámetro en una jerarquía de reemplazo aumenta la utilidad de los reemplazos de método. Cuando el nombre de un parámetro en un método derivado es distinto del nombre de la declaración base, puede resultar difícil determinar si el método es un reemplazo del método base o una nueva sobrecarga del método.|
