---
title: Se ha especificado un valor no válido para el registro de eventos.
ms.date: 07/20/2015
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
ms.openlocfilehash: 36e2bc91a671a22e808d0e30e292471729b1e50b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91083883"
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a>Se ha especificado un valor no válido para el registro de eventos.

Se ha especificado un valor no válido para el registro de eventos. Normalmente, se genera por caracteres no válidos en el nombre, un nombre de archivo en blanco o un nombre de archivo es demasiado largo.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Si el nombre especificado tiene más de ocho caracteres, asegúrese de que no haya ningún conflicto con los nombres de otros registros de eventos. Al determinar si el nombre es único, se evalúan solo los primeros ocho caracteres.  
  
- Si se proporciona una ruta de acceso, asegúrese de que se analiza correctamente.  
  
- Compruebe que no hay ningún carácter no válido en el nombre. Los caracteres que no se pueden usar en un nombre de archivo incluyen `<`, `>`, `:`, `"`, `/`, `\`y `|`.  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para analizar rutas de acceso a archivos](../developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
- [Procedimiento para cambiar el nombre de un archivo](../developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
