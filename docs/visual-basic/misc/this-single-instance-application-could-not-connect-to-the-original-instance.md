---
title: "Esta aplicación de instancia única no pudo conectarse a la instancia original | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 17a3ecd69e0e0974b2a8fc50090097b93dc0def3
ms.lasthandoff: 03/13/2017

---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a>Esta aplicación de una sola instancia no pudo conectar con la instancia original
Esta aplicación de una sola instancia no pudo conectar con la instancia original. Algunas de las posibles causas de este problema son:  
  
-   La instancia original ha dejado de responder.  
  
-   La aplicación no tiene permisos para crear los objetos de kernel. Para obtener más información acerca de los objetos de kernel, consulte [exclusiones mutuas](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2).  
  
     El nombre base de los objetos de kernel procede de concatenar el GUID del ensamblado, el número de la versión principal y el número de la versión secundaria. Por ejemplo, el nombre base podría ser `3639f15d-9547-43da-8145-60da347829915.1`.  
  
## <a name="to-correct-this-error-when-developing-the-application"></a>Para corregir este error al desarrollar la aplicación  
  
1.  Compruebe que la aplicación no entra en un estado que no responde.  
  
2.  Compruebe que la aplicación tiene permisos suficientes para crear objetos de kernel.  
  
3.  Reinicie la instancia original de la aplicación.  
  
4.  Reinicie el equipo para borrar cualquier proceso que pueda estar haciendo uso del recurso necesario para conectarse a la aplicación de instancia original.  
  
5.  Anote las circunstancias en las que se produjo el error y llame a los Servicios de soporte técnico de Microsoft.  
  
## <a name="see-also"></a>Vea también  
 [NIB: Cómo: especificar el comportamiento de las instancias de una aplicación (Visual Basic)](http://msdn.microsoft.com/en-us/48539ad8-d960-4210-beab-ee65f6c6dc6e)   
 [Aspectos básicos del depurador](https://docs.microsoft.com/visualstudio/debugger/debugger-basics)   
 [PAVEOVER compatibilidad de productos y accesibilidad](http://msdn.microsoft.com/en-us/14e1d293-7b6d-40a6-bf3e-a92f8ee6c88c)
