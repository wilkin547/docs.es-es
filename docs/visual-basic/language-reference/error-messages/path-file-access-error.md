---
description: 'Más información acerca de: error de acceso a un archivo o ruta'
title: Error de acceso a la ruta o al archivo
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: d4fc7e716f025c0a482ab414f4a25a2b521634e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795448"
---
# <a name="pathfile-access-error"></a>Error de acceso a la ruta o al archivo

Durante una operación de acceso a archivos o de acceso al disco, el sistema operativo no pudo establecer una conexión entre la ruta de acceso y el nombre de archivo.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Asegúrese de que la especificación del archivo tiene el formato correcto. Un nombre de archivo puede contener una ruta de acceso completa (absoluta) o relativa. Una ruta de acceso completa comienza con el nombre de la unidad (si la ruta de acceso está en otra unidad) y muestra la ruta de acceso explícita de la raíz al archivo. Cualquier ruta de acceso que no sea completa es relativa a la unidad y el directorio actuales.  
  
2. Asegúrese de que no ha intentado guardar un archivo que reemplazaría un archivo de solo lectura existente. Si es así, cambie el atributo de solo lectura del archivo de destino o guarde el archivo con un nombre de archivo diferente.  
  
3. Asegúrese de que no ha intentado abrir un archivo de solo lectura en modo secuencial `Output` o `Append` . Si es así, abra el archivo en `Input` modo o cambie el atributo de solo lectura del archivo.  
  
4. Asegúrese de que no ha intentado cambiar un proyecto de Visual Basic en una base de datos o un documento.  
  
## <a name="see-also"></a>Vea también

- [Tipos de error](../../programming-guide/language-features/error-types.md)
