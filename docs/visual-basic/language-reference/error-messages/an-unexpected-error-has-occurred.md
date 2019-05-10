---
title: Error inesperado porque no se puede conseguir un recurso del sistema operativo necesario para el inicio de una instancia única
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
ms.openlocfilehash: 8130eee93ab5c14043283c28f522da53f9047e85
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64646881"
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
  
## <a name="see-also"></a>Vea también

- [Página de aplicación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Conceptos básicos del depurador](/visualstudio/debugger/debugger-basics)
- [Hable con nosotros](/visualstudio/ide/talk-to-us)
