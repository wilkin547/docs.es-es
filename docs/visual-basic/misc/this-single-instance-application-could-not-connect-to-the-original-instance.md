---
title: Esta aplicación de una sola instancia no pudo conectar con la instancia original
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
ms.openlocfilehash: 7ffa9b185e16cfdf8223ce84e77d1a0e1fa67f65
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942619"
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a>Esta aplicación de una sola instancia no pudo conectar con la instancia original
Esta aplicación de una sola instancia no pudo conectar con la instancia original. Algunas de las posibles causas de este problema son:  
  
- La instancia original ha dejado de responder.  
  
- La aplicación no tiene permisos para crear los objetos de kernel. Para obtener más información acerca de los objetos de kernel, vea [exclusiones mutuas](../../standard/threading/mutexes.md).  
  
     El nombre base de los objetos de kernel procede de concatenar el GUID del ensamblado, el número de la versión principal y el número de la versión secundaria. Por ejemplo, el nombre base podría ser `3639f15d-9547-43da-8145-60da347829915.1`.  
  
## <a name="to-correct-this-error-when-developing-the-application"></a>Para corregir este error al desarrollar la aplicación  
  
1. Compruebe que la aplicación no entra en un estado que no responde.  
  
2. Compruebe que la aplicación tiene permisos suficientes para crear objetos de kernel.  
  
3. Reinicie la instancia original de la aplicación.  
  
4. Reinicie el equipo para borrar cualquier proceso que pueda estar haciendo uso del recurso necesario para conectarse a la aplicación de instancia original.  
  
5. Anote las circunstancias en las que se produjo el error y llame a los Servicios de soporte técnico de Microsoft.  
  
## <a name="see-also"></a>Vea también

- [Conceptos básicos del depurador](/visualstudio/debugger/debugger-basics)
