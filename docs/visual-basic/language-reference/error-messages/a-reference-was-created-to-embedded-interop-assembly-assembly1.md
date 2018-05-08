---
title: Se crea una referencia al ensamblado de interoperabilidad incrustado &#39; &lt;ensamblado1&gt; &#39; debido a una referencia indirecta a dicho ensamblado desde el ensamblado &#39; &lt;assembly2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc40059
- bc40059
helpviewer_keywords:
- VBC40059
- BC40059
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
ms.openlocfilehash: 43a441b6b99988ae1b47969dde9c4bc815820767
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="a-reference-was-created-to-embedded-interop-assembly-39ltassembly1gt39-because-of-an-indirect-reference-to-that-assembly-from-assembly-39ltassembly2gt39"></a>Se crea una referencia al ensamblado de interoperabilidad incrustado &#39; &lt;ensamblado1&gt; &#39; debido a una referencia indirecta a dicho ensamblado desde el ensamblado &#39; &lt;assembly2&gt;&#39;
Se ha creado una referencia al ensamblado de interoperabilidad "\<ensamblado1>" insertado debido a una referencia indirecta a dicho ensamblado desde el ensamblado "\<ensamblado2>". Considere cambiar la propiedad "Incrustar tipos de interoperabilidad" en uno de los ensamblados.  
  
 Ha agregado una referencia a un ensamblado (ensamblado1) cuya propiedad `Embed Interop Types` está establecida en `True`. Esto indica al compilador que incruste la información de tipo de interoperabilidad desde este ensamblado. Sin embargo, el compilador no puede incrustar información de tipo de interoperabilidad desde este ese ensamblado porque otro ensamblado al que ha hecho referencia (ensamblado2) también hace referencia a este ensamblado (ensamblado1) y tiene la propiedad `Embed Interop Types` establecida en `False`.  
  
> [!NOTE]
>  Para el compilador de línea de comandos, el establecimiento de la propiedad `Embed Interop Types` de una referencia a ensamblado en `True` equivale a hacer referencia al ensamblado utilizando la opción `/link`.  
  
 **Id. de error:** BC40059  
  
### <a name="to-address-this-warning"></a>Para resolver esta advertencia  
  
-   Para incrustar información de tipo de interoperabilidad para ambos ensamblados, establezca la propiedad `Embed Interop Types` de todas las referencias a ensamblado1 en `True`.  
  
-   Para quitar la advertencia, puede establecer la propiedad `Embed Interop Types` de ensamblado1 en `False`. En este caso, se proporciona información de tipo de interoperabilidad por un ensamblado de interoperabilidad primario (PIA).  
  
## <a name="see-also"></a>Vea también  
 [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md)  
 [Interoperating with Unmanaged Code](../../../framework/interop/index.md) (Interoperar con código no administrado)
