---
title: Sellar
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f7202e10e41b9f114f42a4502ee2e6694bf3821
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="sealing"></a>Sellar
Una de las características de marcos de trabajo orientado a objetos es que los desarrolladores pueden extender y personalizarlas de maneras no anticipados por los diseñadores de framework. Se trata de la eficacia y el riesgo de diseño extensible. Cuando se diseña el marco, es, por lo tanto, muy importante diseñar cuidadosamente para la extensibilidad cuando se desea y para limitar la extensibilidad cuando es peligroso.  
  
 Un mecanismo eficaz que evita la extensibilidad está sellado. También puede proteger la clase o el miembros individuales. Sellar una clase, impide que los usuarios heredan de la clase. Sellado de un miembro, impide que los usuarios reemplazar a un miembro determinado.  
  
 **X DO NOT** sellar clases sin tener una buena razón para hacerlo.  
  
 Sellar una clase porque no se piensa en un escenario de extensibilidad no es una buena razón. Los usuarios de Framework desean heredar de clases por distintas razones nonobvious, como agregar miembros de comodidad. Vea [clases no selladas](../../../docs/standard/design-guidelines/unsealed-classes.md) para obtener ejemplos de motivos nonobvious los usuarios desean heredar de un tipo.  
  
 Buenos motivos para sellar una clase son los siguientes:  
  
-   La clase es una clase estática. Vea [diseño de clases estáticas](../../../docs/standard/design-guidelines/static-class.md).  
  
-   La clase almacena información confidencial de seguridad en los miembros protegidos heredados.  
  
-   La clase hereda a muchos miembros virtuales y el costo del sellado de forma individual superaría con creces las ventajas de dejar la clase no sellada.  
  
-   La clase es un atributo que requiere la búsqueda en tiempo de ejecución muy rápido. Atributos sellados tienen ligeramente más altos niveles de rendimiento a que no sellados. vea [atributos](../../../docs/standard/design-guidelines/attributes.md).  
  
 **X DO NOT** declarar miembros protegidos o virtuales en tipos sealed.  
  
 Por definición, no se puede heredar de tipos sealed de. Esto significa que no se puede llamar a miembros protegidos en tipos sealed, y no se puede invalidar métodos virtuales en tipos sealed.  
  
 **Considere la posibilidad de ✓** sellar los miembros reemplazados.  
  
 Problemas que pueden derivarse de introducción a los miembros virtuales (se describe en [miembros virtuales](../../../docs/standard/design-guidelines/virtual-members.md)) se aplican a invalidaciones, aunque a ligeramente menor grado. Sellar una invalidación intercepta estos problemas desde ese punto en la jerarquía de herencia.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [Clases no selladas](../../../docs/standard/design-guidelines/unsealed-classes.md)
