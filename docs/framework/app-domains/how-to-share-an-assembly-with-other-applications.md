---
title: Procedimiento para compartir un ensamblado con otras aplicaciones
description: Vea cómo compartir un ensamblado con otras aplicaciones en .NET. Los ensamblados pueden ser privados (el valor predeterminado) o compartidos. Para compartir un ensamblado, colóquelo en la GAC.
ms.date: 08/19/2019
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: 1056f8b555713d5d67488537e6c06cc457c4d312
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242544"
---
# <a name="how-to-share-an-assembly-with-other-applications"></a>Procedimiento para compartir un ensamblado con otras aplicaciones

Los ensamblados pueden ser privados o compartidos: de forma predeterminada, la mayoría de los programas sencillos constan de un ensamblado privado porque no se diseñaron para ser usados por otras aplicaciones.  

Para compartir un ensamblado con otras aplicaciones, debe colocarse en la [caché global de ensamblados](gac.md).  
  
Para compartir un ensamblado:
  
1. Cree el ensamblado. Para obtener más información, vea [Creación de ensamblados](../../standard/assembly/create.md).  
  
2. Asigne un nombre seguro al ensamblado. Para obtener más información, vea [Cómo: Firmar un ensamblado con un nombre seguro](../../standard/assembly/sign-strong-name.md).  
  
3. Asigne la información de versión al ensamblado. Para obtener más información, vea [Versiones de los ensamblados](../../standard/assembly/versioning.md).  
  
4. Agregue el ensamblado a la caché global de ensamblados. Para obtener más información, vea [Cómo: Instalar un ensamblado en la caché global de ensamblados](install-assembly-into-gac.md).  
  
5. Obtenga acceso a los tipos que contiene el ensamblado desde otras aplicaciones. Para obtener más información, vea [Cómo: Hacer referencia a un ensamblado con nombre seguro](../../standard/assembly/reference-strong-named.md).  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../api/index.md)
- [Conceptos de programación (Visual Basic)](../../../api/index.md)
- [Programación con ensamblados](../../standard/assembly/index.md)
