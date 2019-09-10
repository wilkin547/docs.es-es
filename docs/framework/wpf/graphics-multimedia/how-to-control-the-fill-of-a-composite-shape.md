---
title: Procedimiento Controlar el relleno de una forma compuesta
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], composite [WPF], controlling fill
- composite shapes [WPF], controlling fill
- graphics [WPF], composite shapes
- fill [WPF], controlling
ms.assetid: c1c94575-9eca-48a5-a49a-2ec65259f229
ms.openlocfilehash: 89f69d392e8838af99538c759a2f06453e1bcd60
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855901"
---
# <a name="how-to-control-the-fill-of-a-composite-shape"></a>Procedimiento Controlar el relleno de una forma compuesta

La <xref:System.Windows.Media.GeometryGroup.FillRule%2A> propiedad <xref:System.Windows.Media.GeometryGroup> de o<xref:System.Windows.Media.PathGeometry>, especifica una "regla" que la forma compuesta utiliza para determinar si un punto determinado forma parte de la geometría. Existen dos valores posibles para <xref:System.Windows.Media.FillRule>: <xref:System.Windows.Media.FillRule.EvenOdd> y <xref:System.Windows.Media.FillRule.Nonzero>. En las secciones siguientes se describe cómo usar estas dos reglas.

**EvenOdd:** Esta regla determina si un punto está en la región de relleno dibujando un rayo desde ese punto hasta el infinito en cualquier dirección y contando el número de segmentos de trazado dentro de la forma especificada que cruza el rayo. Si este número es impar, el punto está dentro; si es par, el punto está fuera.

Por ejemplo, el código XAML siguiente crea una forma compuesta formada por una serie de anillos concéntricos (destino) <xref:System.Windows.Media.GeometryGroup.FillRule%2A> con un <xref:System.Windows.Media.FillRule.EvenOdd>establecido en.

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleEvenOddValue](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillruleevenoddvalue)]

La siguiente ilustración muestra la forma creada en el ejemplo anterior.

![Círculo compuesto por una serie de anillos concéntricos con colores alternos.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-property.png)

En la ilustración anterior, observe que no se rellenan el centro y el tercer anillo. Esto se debe a que un radio dibujado desde cualquier punto dentro de esos dos anillos pasa a través de un número par de segmentos. Vea la ilustración siguiente:

![Diagrama que muestra los rayos de EvenOdd dibujados en el círculo.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-rays.png)

**NonZero:** Esta regla determina si un punto está en la región de relleno del trazado dibujando un rayo desde ese punto hasta el infinito en cualquier dirección y examinando después los lugares donde un segmento de la forma cruza el rayo. Partiendo de cero, sume una ubicación cada vez que un segmento cruce el radio de izquierda a derecha y reste una ubicación cada vez que un segmento de trazado cruce el radio de derecha a izquierda. Después de contar el número de veces que cruza, si el resultado es cero, el punto está fuera del trazado. De lo contrario, está dentro.

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValueEllipseGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovalueellipsegeometry)]

Con el ejemplo anterior, un valor de <xref:System.Windows.Media.FillRule.Nonzero> para <xref:System.Windows.Media.GeometryGroup.FillRule%2A> proporciona la siguiente ilustración como resultado:

![Círculo compuesto por una serie de anillos concéntricos todos rellenados con el mismo color.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-nonzero.png)

Como puede ver, se rellenan todos los anillos. Esto es porque todos los segmentos se ejecutan en la misma dirección de modo que un radio dibujado desde cualquier punto cruzará uno o más segmentos y la suma de las veces que cruza no será igual a cero. Por ejemplo, en la siguiente ilustración, las flechas rojas representan la dirección en la que se dibujan los segmentos y la flecha blanca representa un rayo arbitrario que se ejecuta desde un punto en el anillo más interno. A partir de un valor de cero, para cada segmento que cruza el radio, se agrega un valor de uno porque el segmento cruza el radio de izquierda a derecha.

![Diagrama que muestra el valor de la propiedad FillRule igual a NonZero.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-equal-nonzero.png)

Para demostrar mejor el comportamiento de <xref:System.Windows.Media.FillRule.Nonzero> la regla, se requiere una forma más compleja con segmentos que se ejecuten en diferentes direcciones. En el código XAML siguiente se crea una forma similar <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.EllipseGeometry> a la del ejemplo anterior, salvo que se crea con un en su lugar, que crea cuatro arcos concéntricos en lugar de círculos concéntricos totalmente cerrados.

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValuePathGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovaluepathgeometry)]

La siguiente ilustración muestra la forma creada en el ejemplo anterior.

![Un círculo compuesto por una serie de anillos concéntricos con colores alternativos con el tercer arco no rellenado.](./media/how-to-control-the-fill-of-a-composite-shape/pathgeometry-concentric-arcs.png)

Observe que no se rellena el tercer arco contando desde el centro. En la ilustración siguiente se muestra por qué es. En la ilustración, las flechas rojas representan la dirección en que se dibujan los segmentos. Las dos flechas blancas representan dos radios arbitrarios que parten desde un punto en la región "no rellena". Como puede observarse en la ilustración, la suma de los valores de un radio determinado que cruza los segmentos en su trazado es cero. Como se ha definido anteriormente, una suma de cero significa que el punto no forma parte de la geometría (no es parte del relleno), mientras que la suma que *no* es igual a cero, incluido un valor negativo, sí forma parte de la geometría.

![Diagrama que muestra los rayos arbitrarios que cruzan segmentos.](./media/how-to-control-the-fill-of-a-composite-shape/arbitrary-ray-cross-segment.png)

> [!NOTE]
> Para los fines de <xref:System.Windows.Media.FillRule>, todas las formas se consideran cerradas. Si hay un hueco en un segmento, dibuje una línea imaginaria para cerrarlo. En el ejemplo anterior, hay huecos pequeños en los anillos. Por tanto, se podría esperar que un radio que atraviesa el hueco ofrezca un resultado distinto al de un radio que se ejecuta en otra dirección. A continuación se muestra una ilustración ampliada de uno de estos huecos y el "segmento imaginario" (segmento que se dibuja con el <xref:System.Windows.Media.FillRule>fin de aplicar el) que lo cierra.

![Diagrama que muestra segmentos FillRule que siempre están cerrados.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-closed-segments.png)

## <a name="example"></a>Ejemplo

## <a name="see-also"></a>Vea también

- [Crear una forma compuesta](how-to-create-a-composite-shape.md)
- [Información general sobre geometría](geometry-overview.md)
