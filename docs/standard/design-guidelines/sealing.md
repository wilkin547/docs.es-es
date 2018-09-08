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
ms.openlocfilehash: 6d8c445de44a69f6c0cb1eaefa0e59d682288318
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44199926"
---
# <a name="sealing"></a>Sellar
Una de las características de marcos de trabajo orientado a objetos es que los desarrolladores pueden ampliar y personalizarlos en modos imprevistos por los diseñadores de framework. Se trata de la eficacia y el peligro de diseño extensible. Al diseñar su marco, es, por lo tanto, muy importante para diseñar cuidadosamente para la extensibilidad cuando lo desee y para limitar la extensibilidad cuando resulta peligroso.  
  
 Un mecanismo eficaz que impide la extensibilidad de sellado. Puede sellar clases o miembros individuales. Sellar una clase, impide que los usuarios hereden de la clase. Sellado de un miembro, impide que los usuarios invalidar a un miembro determinado.  
  
 **X DO NOT** sellar clases sin tener una buena razón para hacerlo.  
  
 Sellar una clase porque no se puede pensar en un escenario de extensibilidad no es una buena razón. Los usuarios de plataformas como heredar de clases por diversos motivos nonobvious, como agregar miembros de comodidad. Consulte [clases no selladas](../../../docs/standard/design-guidelines/unsealed-classes.md) para obtener ejemplos de motivos nonobvious los usuarios desean hereda de un tipo.  
  
 Buenas razones para sellar una clase incluyen lo siguiente:  
  
-   La clase es una clase estática. Consulte [diseño de clases estáticas](../../../docs/standard/design-guidelines/static-class.md).  
  
-   La clase almacena los secretos de seguridad en los miembros protegidos heredados.  
  
-   La clase hereda a muchos miembros virtuales y el costo de sellar ellos individualmente superaría con creces las ventajas de salir de la clase no sellada.  
  
-   La clase es un atributo que requiere la búsqueda en tiempo de ejecución muy rápida. Atributos sealed tienen niveles de rendimiento ligeramente superiores que no sellado que. consulte [atributos](../../../docs/standard/design-guidelines/attributes.md).  
  
 **X DO NOT** declarar miembros protegidos o virtuales en tipos sealed.  
  
 Por definición, tipos sellados no se puede heredar de. Esto significa que los miembros protegidos en tipos sellados no se puede llamar, y no se puede invalidar los métodos virtuales en tipos sealed.  
  
 **✓ CONSIDER** sellar los miembros reemplazados.  
  
 Problemas que pueden derivarse de introducción a los miembros virtuales (se describe en [miembros virtuales](../../../docs/standard/design-guidelines/virtual-members.md)) se aplican a invalidaciones, aunque en un grado ligeramente menor. Sellar una invalidación intercepta estos problemas a partir de ese punto en la jerarquía de herencia.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [Clases no selladas](../../../docs/standard/design-guidelines/unsealed-classes.md)
