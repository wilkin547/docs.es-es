---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 334bab97a04ed464dce6944692b04a9ed1295296
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54613833"
---
# <a name="mustunderstandbehavior"></a>MustUnderstandBehavior
MustUnderstandBehavior  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase MustUnderstandBehavior no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase MustUnderstandBehavior tiene la propiedad siguiente:  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Cuando `true`, todos los encabezados SOAP con el atributo `MustUnderstand` que no se administran provocan que el comportamiento produzca una excepción.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Description.MustUnderstandBehavior>
