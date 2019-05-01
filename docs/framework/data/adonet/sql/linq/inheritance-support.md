---
title: Compatibilidad de herencia
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: 668f4f1dd284550e644ce6b8a4491ca47105575e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033558"
---
# <a name="inheritance-support"></a>Compatibilidad de herencia
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite *asignación de tabla única*. En otras palabras, en una sola tabla de base de datos se almacena una jerarquía de herencia completa. La tabla contiene la unión simplificada de todas las posibles columnas de datos de toda la jerarquía. (Una unión es el resultado de combinar dos tablas en una sola tabla que contiene las filas que estaban presentes en cualquiera de las tablas originales.) Cada fila tiene valores nulos en las columnas que no corresponden al tipo de la instancia representada por la fila.  
  
 La estrategia de asignación de tabla única es la representación más simple de la herencia y presenta buenas características de rendimiento para muchas categorías diferentes de consultas.  
  
 Para implementar esta asignación en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], debe especificar los atributos y las propiedades de los atributos en la clase raíz de la jerarquía de herencia. Para obtener más información, vea [Cómo: Asignar jerarquías de herencia](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).  
  
 Los desarrolladores que usan Visual Studio también pueden usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para asignar jerarquías de herencia.  
  
## <a name="see-also"></a>Vea también

- [Información general](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
