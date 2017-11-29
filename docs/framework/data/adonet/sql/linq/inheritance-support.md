---
title: Compatibilidad de herencia
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b6ee6779814adeab73e21477137db1ed71a23a88
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="inheritance-support"></a>Compatibilidad de herencia
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]admite *asignación de tabla única*. En otras palabras, en una sola tabla de base de datos se almacena una jerarquía de herencia completa. La tabla contiene la unión simplificada de todas las posibles columnas de datos de toda la jerarquía. (Una unión es el resultado de combinar dos tablas en una sola tabla que contiene las filas que estaban presentes en cualquiera de las tablas originales.) Cada fila tiene valores nulos en las columnas que no corresponden al tipo de la instancia representada por la fila.  
  
 La estrategia de asignación de tabla única es la representación más simple de la herencia y presenta buenas características de rendimiento para muchas categorías diferentes de consultas.  
  
 Para implementar esta asignación en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], debe especificar los atributos y las propiedades de los atributos en la clase raíz de la jerarquía de herencia. Para obtener más información, consulte [Cómo: asignar jerarquías de herencia](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).  
  
 Los desarrolladores de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] también pueden utilizar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para asignar jerarquías de herencia.  
  
## <a name="see-also"></a>Vea también  
 [Información general](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
