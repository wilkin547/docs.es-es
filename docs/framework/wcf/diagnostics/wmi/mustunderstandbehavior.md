---
title: MustUnderstandBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dca98f1d8d5f868285ecf11c01122f795ee6cfd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="mustunderstandbehavior"></a>MustUnderstandBehavior
MustUnderstandBehavior  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
 Tipo de acceso: solo lectura  
  
 Cuando `true`, todos los encabezados SOAP con el atributo `MustUnderstand` que no se administran provocan que el comportamiento produzca una excepción.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>
