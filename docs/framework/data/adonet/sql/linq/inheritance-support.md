---
title: Compatibilidad de herencia
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: 7673e69458d5c1af854747c43ba463332a9cd588
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158258"
---
# <a name="inheritance-support"></a>Compatibilidad de herencia

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite *la asignación de tabla única*. En otras palabras, en una sola tabla de base de datos se almacena una jerarquía de herencia completa. La tabla contiene la unión simplificada de todas las posibles columnas de datos de toda la jerarquía. (Una Unión es el resultado de combinar dos tablas en una tabla que tiene las filas que estaban presentes en cualquiera de las tablas originales). Cada fila tiene valores NULL en las columnas que no se aplican al tipo de la instancia representada por la fila.  
  
 La estrategia de asignación de tabla única es la representación más simple de la herencia y presenta buenas características de rendimiento para muchas categorías diferentes de consultas.  
  
 Para implementar esta asignación en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], debe especificar los atributos y las propiedades de los atributos en la clase raíz de la jerarquía de herencia. Para obtener más información, vea [Cómo: asignar jerarquías de herencia](how-to-map-inheritance-hierarchies.md).  
  
 Los desarrolladores que usan Visual Studio también pueden usar el Object Relational Designer para asignar jerarquías de herencia.  
  
## <a name="see-also"></a>Vea también

- [Información general](background-information.md)
