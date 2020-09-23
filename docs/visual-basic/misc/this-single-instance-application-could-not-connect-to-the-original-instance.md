---
title: Esta aplicación de una sola instancia no pudo conectar con la instancia original
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
ms.openlocfilehash: 8e2caa158c3874d216671979430a03b11bf60066
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095686"
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a>Esta aplicación de una sola instancia no pudo conectar con la instancia original

Esta aplicación de una sola instancia no pudo conectar con la instancia original. Algunas de las posibles causas de este problema son:  
  
- La instancia original ha dejado de responder.  
  
- La aplicación no tiene permisos para crear los objetos de kernel. Para obtener más información sobre los objetos de kernel, consulte [exclusiones mutuas](../../standard/threading/mutexes.md).  
  
     El nombre base de los objetos de kernel procede de concatenar el GUID del ensamblado, el número de la versión principal y el número de la versión secundaria. Por ejemplo, el nombre base podría ser `3639f15d-9547-43da-8145-60da347829915.1`.  
  
## <a name="to-correct-this-error-when-developing-the-application"></a>Para corregir este error al desarrollar la aplicación  
  
1. Compruebe que la aplicación no entra en un estado que no responde.  
  
2. Compruebe que la aplicación tiene permisos suficientes para crear objetos de kernel.  
  
3. Reinicie la instancia original de la aplicación.  
  
4. Reinicie el equipo para borrar cualquier proceso que pueda estar haciendo uso del recurso necesario para conectarse a la aplicación de instancia original.  
  
5. Anote las circunstancias en las que se produjo el error y llame a los Servicios de soporte técnico de Microsoft.  
  
## <a name="see-also"></a>Vea también

- [Conceptos básicos del depurador](/visualstudio/debugger/debugger-feature-tour)
