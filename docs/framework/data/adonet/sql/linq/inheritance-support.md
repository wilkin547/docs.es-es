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
# <a name="inheritance-support"></a><span data-ttu-id="508e1-102">Compatibilidad de herencia</span><span class="sxs-lookup"><span data-stu-id="508e1-102">Inheritance Support</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="508e1-103">admite *la asignación de tabla única*.</span><span class="sxs-lookup"><span data-stu-id="508e1-103">supports *single-table mapping*.</span></span> <span data-ttu-id="508e1-104">En otras palabras, en una sola tabla de base de datos se almacena una jerarquía de herencia completa.</span><span class="sxs-lookup"><span data-stu-id="508e1-104">In other words, a complete inheritance hierarchy is stored in a single database table.</span></span> <span data-ttu-id="508e1-105">La tabla contiene la unión simplificada de todas las posibles columnas de datos de toda la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="508e1-105">The table contains the flattened union of all possible data columns for the whole hierarchy.</span></span> <span data-ttu-id="508e1-106">(Una Unión es el resultado de combinar dos tablas en una tabla que tiene las filas que estaban presentes en cualquiera de las tablas originales). Cada fila tiene valores NULL en las columnas que no se aplican al tipo de la instancia representada por la fila.</span><span class="sxs-lookup"><span data-stu-id="508e1-106">(A union is the result of combining two tables into one table that has the rows that were present in either of the original tables.) Each row has nulls in the columns that do not apply to the type of the instance represented by the row.</span></span>  
  
 <span data-ttu-id="508e1-107">La estrategia de asignación de tabla única es la representación más simple de la herencia y presenta buenas características de rendimiento para muchas categorías diferentes de consultas.</span><span class="sxs-lookup"><span data-stu-id="508e1-107">The single-table mapping strategy is the simplest representation of inheritance and provides good performance characteristics for many different categories of queries.</span></span>  
  
 <span data-ttu-id="508e1-108">Para implementar esta asignación en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], debe especificar los atributos y las propiedades de los atributos en la clase raíz de la jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="508e1-108">To implement this mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy.</span></span> <span data-ttu-id="508e1-109">Para obtener más información, vea [Cómo: asignar jerarquías de herencia](how-to-map-inheritance-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="508e1-109">For more information, see [How to: Map Inheritance Hierarchies](how-to-map-inheritance-hierarchies.md).</span></span>  
  
 <span data-ttu-id="508e1-110">Los desarrolladores que usan Visual Studio también pueden usar el Object Relational Designer para asignar jerarquías de herencia.</span><span class="sxs-lookup"><span data-stu-id="508e1-110">Developers using Visual Studio can also use the Object Relational Designer to map inheritance hierarchies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="508e1-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="508e1-111">See also</span></span>

- [<span data-ttu-id="508e1-112">Información general</span><span class="sxs-lookup"><span data-stu-id="508e1-112">Background Information</span></span>](background-information.md)
