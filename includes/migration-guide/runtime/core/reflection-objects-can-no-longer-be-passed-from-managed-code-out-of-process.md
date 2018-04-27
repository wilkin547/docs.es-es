### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>Los objetos Reflection ya no se pueden pasar desde el código administrado a los clientes DCOM fuera de proceso

|   |   |
|---|---|
|Detalles|Los objetos de reflexión ya no se pueden pasar desde el código administrado a los clientes DCOM fuera de proceso. Afecta a los siguientes tipos:<ul><li><xref:System.Reflection.Assembly?displayProperty=name></li><li><xref:System.Reflection.MemberInfo?displayProperty=name> (y sus tipos derivados, incluidos <xref:System.Reflection.FieldInfo?displayProperty=name>, <xref:System.Reflection.MethodInfo?displayProperty=name>, <xref:System.Type?displayProperty=name> y <xref:System.Reflection.TypeInfo?displayProperty=name>)</li><li><xref:System.Reflection.MethodBody?displayProperty=name></li><li><xref:System.Reflection.Module?displayProperty=name></li><li><xref:System.Reflection.ParameterInfo?displayProperty=name>.</li></ul>Las llamadas a <code>IMarshal</code> para el objeto devuelven <code>E_NOINTERFACE</code>.|
|Sugerencia|Actualice el código de serialización para que funcione con objetos distintos a Reflection.|
|Ámbito|Secundaria|
|Versión|4.6|
|Tipo|Tiempo de ejecución|

