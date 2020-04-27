---
title: Procedimiento para compartir un ensamblado con otras aplicaciones
ms.date: 08/19/2019
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: b4c183c3fc0b04121be8bbc2db4027887cbc3132
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644289"
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
