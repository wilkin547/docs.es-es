---
title: Demasiados archivos
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: cd168ce86569d2d7558e21a5b4cc5ef385b28313
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873552"
---
# <a name="too-many-files"></a>Demasiados archivos

Se han creado más archivos en el directorio raíz que los que permite el sistema operativo, o se han abierto más archivos que el número especificado en la configuración **archivos =** en el archivo de CONFIG.SYS.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Si el programa está abriendo, cerrando o guardando archivos en el directorio raíz, cambie el programa para que use un subdirectorio.  
  
2. Aumente el número de archivos especificados en la configuración de **archivos =** en el archivo de CONFIG.SYS y reinicie el equipo.  
  
## <a name="see-also"></a>Consulte también

- [Tipos de errores](../../programming-guide/language-features/error-types.md)
