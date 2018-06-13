---
title: Compatibilidad de herencia
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: 3d396632902b178eee34801a9716d8aa222a08d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359567"
---
# <a name="inheritance-support"></a><span data-ttu-id="1c5dd-102">Compatibilidad de herencia</span><span class="sxs-lookup"><span data-stu-id="1c5dd-102">Inheritance Support</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="1c5dd-103"> admite *asignación de tabla única*.</span><span class="sxs-lookup"><span data-stu-id="1c5dd-103"> supports *single-table mapping*.</span></span> <span data-ttu-id="1c5dd-104">En otras palabras, en una sola tabla de base de datos se almacena una jerarquía de herencia completa.</span><span class="sxs-lookup"><span data-stu-id="1c5dd-104">In other words, a complete inheritance hierarchy is stored in a single database table.</span></span> <span data-ttu-id="1c5dd-105">La tabla contiene la unión simplificada de todas las posibles columnas de datos de toda la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="1c5dd-105">The table contains the flattened union of all possible data columns for the whole hierarchy.</span></span> <span data-ttu-id="1c5dd-106">(Una unión es el resultado de combinar dos tablas en una sola tabla que contiene las filas que estaban presentes en cualquiera de las tablas originales.) Cada fila tiene valores nulos en las columnas que no corresponden al tipo de la instancia representada por la fila.</span><span class="sxs-lookup"><span data-stu-id="1c5dd-106">(A union is the result of combining two tables into one table that has the rows that were present in either of the original tables.) Each row has nulls in the columns that do not apply to the type of the instance represented by the row.</span></span>  
  
 <span data-ttu-id="1c5dd-107">La estrategia de asignación de tabla única es la representación más simple de la herencia y presenta buenas características de rendimiento para muchas categorías diferentes de consultas.</span><span class="sxs-lookup"><span data-stu-id="1c5dd-107">The single-table mapping strategy is the simplest representation of inheritance and provides good performance characteristics for many different categories of queries.</span></span>  
  
 <span data-ttu-id="1c5dd-108">Para implementar esta asignación en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], debe especificar los atributos y las propiedades de los atributos en la clase raíz de la jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="1c5dd-108">To implement this mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy.</span></span> <span data-ttu-id="1c5dd-109">Para obtener más información, consulte [Cómo: asignar jerarquías de herencia](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="1c5dd-109">For more information, see [How to: Map Inheritance Hierarchies](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).</span></span>  
  
 <span data-ttu-id="1c5dd-110">Los desarrolladores que utilizan Visual Studio también pueden usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para asignar jerarquías de herencia.</span><span class="sxs-lookup"><span data-stu-id="1c5dd-110">Developers using Visual Studio can also use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map inheritance hierarchies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c5dd-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c5dd-111">See Also</span></span>  
 [<span data-ttu-id="1c5dd-112">Información general</span><span class="sxs-lookup"><span data-stu-id="1c5dd-112">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
