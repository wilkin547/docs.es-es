---
description: 'Más información acerca de: se ha producido un error inesperado porque no se puede adquirir un recurso del sistema operativo necesario para el inicio de una sola instancia'
title: Error inesperado porque no se puede conseguir un recurso del sistema operativo necesario para el inicio de una instancia única
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
ms.openlocfilehash: 76f7bd43c05ea3bd46b352a791debac984ca8fcd
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102103613"
---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a>Error inesperado porque no se puede conseguir un recurso del sistema operativo necesario para el inicio de una instancia única

La aplicación no pudo obtener un recurso de sistema operativo necesario. Algunas de las posibles causas de este problema son:  
  
- La aplicación no tiene permisos para crear objetos de sistema operativo con nombre.  
  
- Common Language Runtime no tiene permisos para crear archivos asignados a memoria.  
  
- La aplicación necesita acceder a un objeto de sistema operativo, pero hay otro proceso que lo está utilizando.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Confirme que la aplicación tiene permisos suficientes para crear objetos de sistema operativo con nombre.  
  
2. Confirme que Common Language Runtime tiene permisos suficientes para crear archivos asignados a memoria.  
  
3. Reinicie el equipo para borrar cualquier proceso que pueda estar haciendo uso del recurso necesario para conectarse a la aplicación de instancia original.  
  
4. Anote las circunstancias en las que se ha produjo el error y llame a los Servicios de soporte técnico de Microsoft.  
  
## <a name="see-also"></a>Consulte también

- [Página de aplicación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Conceptos básicos del depurador](/visualstudio/debugger/debugger-basics)
- [Opciones de comentarios de Visual Studio](/visualstudio/ide/feedback-options)
