---
description: 'Más información acerca de: colecciones de esquemas de ODBC'
title: Colecciones de esquemas de ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ceac67e49914db7010e315a2dfcdb630bea1e29f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786204"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="34f90-103">Colecciones de esquemas de ODBC</span><span class="sxs-lookup"><span data-stu-id="34f90-103">ODBC Schema Collections</span></span>

<span data-ttu-id="34f90-104">En esta sección se describe la compatibilidad de las colecciones de esquemas con los controladores ODBC de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="34f90-104">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="34f90-105">Controlador ODBC para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="34f90-105">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="34f90-106">El controlador ODBC de Microsoft SQL Server admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="34f90-106">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="34f90-107">Tablas</span><span class="sxs-lookup"><span data-stu-id="34f90-107">Tables</span></span>

- <span data-ttu-id="34f90-108">Índices</span><span class="sxs-lookup"><span data-stu-id="34f90-108">Indexes</span></span>

- <span data-ttu-id="34f90-109">Columnas</span><span class="sxs-lookup"><span data-stu-id="34f90-109">Columns</span></span>

- <span data-ttu-id="34f90-110">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="34f90-110">Procedures</span></span>

- <span data-ttu-id="34f90-111">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="34f90-111">ProcedureColumns</span></span>

- <span data-ttu-id="34f90-112">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="34f90-112">ProcedureParameters</span></span>

- <span data-ttu-id="34f90-113">Vistas</span><span class="sxs-lookup"><span data-stu-id="34f90-113">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="34f90-114">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="34f90-114">Tables and Views</span></span>

|<span data-ttu-id="34f90-115">ColumnName</span><span class="sxs-lookup"><span data-stu-id="34f90-115">ColumnName</span></span>|<span data-ttu-id="34f90-116">DataType</span><span class="sxs-lookup"><span data-stu-id="34f90-116">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="34f90-117">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="34f90-117">TABLE_CAT</span></span>|<span data-ttu-id="34f90-118">String</span><span class="sxs-lookup"><span data-stu-id="34f90-118">String</span></span>|
|<span data-ttu-id="34f90-119">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="34f90-119">TABLE_SCHEM</span></span>|<span data-ttu-id="34f90-120">String</span><span class="sxs-lookup"><span data-stu-id="34f90-120">String</span></span>|
|<span data-ttu-id="34f90-121">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-121">TABLE_NAME</span></span>|<span data-ttu-id="34f90-122">String</span><span class="sxs-lookup"><span data-stu-id="34f90-122">String</span></span>|
|<span data-ttu-id="34f90-123">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-123">TABLE_TYPE</span></span>|<span data-ttu-id="34f90-124">String</span><span class="sxs-lookup"><span data-stu-id="34f90-124">String</span></span>|
|<span data-ttu-id="34f90-125">COMENTARIOS</span><span class="sxs-lookup"><span data-stu-id="34f90-125">REMARKS</span></span>|<span data-ttu-id="34f90-126">String</span><span class="sxs-lookup"><span data-stu-id="34f90-126">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="34f90-127">Índices</span><span class="sxs-lookup"><span data-stu-id="34f90-127">Indexes</span></span>

|<span data-ttu-id="34f90-128">ColumnName</span><span class="sxs-lookup"><span data-stu-id="34f90-128">ColumnName</span></span>|<span data-ttu-id="34f90-129">DataType</span><span class="sxs-lookup"><span data-stu-id="34f90-129">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="34f90-130">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="34f90-130">TABLE_CAT</span></span>|<span data-ttu-id="34f90-131">String</span><span class="sxs-lookup"><span data-stu-id="34f90-131">String</span></span>|
|<span data-ttu-id="34f90-132">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="34f90-132">TABLE_SCHEM</span></span>|<span data-ttu-id="34f90-133">String</span><span class="sxs-lookup"><span data-stu-id="34f90-133">String</span></span>|
|<span data-ttu-id="34f90-134">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-134">TABLE_NAME</span></span>|<span data-ttu-id="34f90-135">String</span><span class="sxs-lookup"><span data-stu-id="34f90-135">String</span></span>|
|<span data-ttu-id="34f90-136">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="34f90-136">NON_UNIQUE</span></span>|<span data-ttu-id="34f90-137">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-137">Int16</span></span>|
|<span data-ttu-id="34f90-138">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="34f90-138">INDEX_QUALIFIER</span></span>|<span data-ttu-id="34f90-139">String</span><span class="sxs-lookup"><span data-stu-id="34f90-139">String</span></span>|
|<span data-ttu-id="34f90-140">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-140">INDEX_NAME</span></span>|<span data-ttu-id="34f90-141">String</span><span class="sxs-lookup"><span data-stu-id="34f90-141">String</span></span>|
|<span data-ttu-id="34f90-142">TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-142">TYPE</span></span>|<span data-ttu-id="34f90-143">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-143">Int16</span></span>|
|<span data-ttu-id="34f90-144">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="34f90-144">ORDINAL_POSITION</span></span>|<span data-ttu-id="34f90-145">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-145">Int16</span></span>|
|<span data-ttu-id="34f90-146">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-146">COLUMN_NAME</span></span>|<span data-ttu-id="34f90-147">String</span><span class="sxs-lookup"><span data-stu-id="34f90-147">String</span></span>|
|<span data-ttu-id="34f90-148">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="34f90-148">ASC_OR_DESC</span></span>|<span data-ttu-id="34f90-149">String</span><span class="sxs-lookup"><span data-stu-id="34f90-149">String</span></span>|
|<span data-ttu-id="34f90-150">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="34f90-150">CARDINALITY</span></span>|<span data-ttu-id="34f90-151">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-151">Int32</span></span>|
|<span data-ttu-id="34f90-152">PAGES</span><span class="sxs-lookup"><span data-stu-id="34f90-152">PAGES</span></span>|<span data-ttu-id="34f90-153">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-153">Int32</span></span>|
|<span data-ttu-id="34f90-154">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="34f90-154">FILTER_CONDITION</span></span>|<span data-ttu-id="34f90-155">String</span><span class="sxs-lookup"><span data-stu-id="34f90-155">String</span></span>|
|<span data-ttu-id="34f90-156">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="34f90-156">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="34f90-157">String</span><span class="sxs-lookup"><span data-stu-id="34f90-157">String</span></span>|
|<span data-ttu-id="34f90-158">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-158">SS_DATA_TYPE</span></span>|<span data-ttu-id="34f90-159">Byte</span><span class="sxs-lookup"><span data-stu-id="34f90-159">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="34f90-160">Columnas</span><span class="sxs-lookup"><span data-stu-id="34f90-160">Columns</span></span>

|<span data-ttu-id="34f90-161">ColumnName</span><span class="sxs-lookup"><span data-stu-id="34f90-161">ColumnName</span></span>|<span data-ttu-id="34f90-162">DataType</span><span class="sxs-lookup"><span data-stu-id="34f90-162">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="34f90-163">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="34f90-163">TABLE_CAT</span></span>|<span data-ttu-id="34f90-164">String</span><span class="sxs-lookup"><span data-stu-id="34f90-164">String</span></span>|
|<span data-ttu-id="34f90-165">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="34f90-165">TABLE_SCHEM</span></span>|<span data-ttu-id="34f90-166">String</span><span class="sxs-lookup"><span data-stu-id="34f90-166">String</span></span>|
|<span data-ttu-id="34f90-167">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-167">TABLE_NAME</span></span>|<span data-ttu-id="34f90-168">String</span><span class="sxs-lookup"><span data-stu-id="34f90-168">String</span></span>|
|<span data-ttu-id="34f90-169">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-169">COLUMN_NAME</span></span>|<span data-ttu-id="34f90-170">String</span><span class="sxs-lookup"><span data-stu-id="34f90-170">String</span></span>|
|<span data-ttu-id="34f90-171">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-171">DATA_TYPE</span></span>|<span data-ttu-id="34f90-172">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-172">Int16</span></span>|
|<span data-ttu-id="34f90-173">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-173">TYPE_NAME</span></span>|<span data-ttu-id="34f90-174">String</span><span class="sxs-lookup"><span data-stu-id="34f90-174">String</span></span>|
|<span data-ttu-id="34f90-175">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="34f90-175">COLUMN_SIZE</span></span>|<span data-ttu-id="34f90-176">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-176">Int32</span></span>|
|<span data-ttu-id="34f90-177">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="34f90-177">BUFFER_LENGTH</span></span>|<span data-ttu-id="34f90-178">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-178">Int32</span></span>|
|<span data-ttu-id="34f90-179">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="34f90-179">DECIMAL_DIGITS</span></span>|<span data-ttu-id="34f90-180">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-180">Int16</span></span>|
|<span data-ttu-id="34f90-181">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="34f90-181">NUM_PREC_RADIX</span></span>|<span data-ttu-id="34f90-182">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-182">Int16</span></span>|
|<span data-ttu-id="34f90-183">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="34f90-183">NULLABLE</span></span>|<span data-ttu-id="34f90-184">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-184">Int16</span></span>|
|<span data-ttu-id="34f90-185">COMENTARIOS</span><span class="sxs-lookup"><span data-stu-id="34f90-185">REMARKS</span></span>|<span data-ttu-id="34f90-186">String</span><span class="sxs-lookup"><span data-stu-id="34f90-186">String</span></span>|
|<span data-ttu-id="34f90-187">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="34f90-187">COLUMN_DEF</span></span>|<span data-ttu-id="34f90-188">String</span><span class="sxs-lookup"><span data-stu-id="34f90-188">String</span></span>|
|<span data-ttu-id="34f90-189">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-189">SQL_DATA_TYPE</span></span>|<span data-ttu-id="34f90-190">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-190">Int16</span></span>|
|<span data-ttu-id="34f90-191">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="34f90-191">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="34f90-192">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-192">Int16</span></span>|
|<span data-ttu-id="34f90-193">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="34f90-193">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="34f90-194">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-194">Int32</span></span>|
|<span data-ttu-id="34f90-195">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="34f90-195">ORDINAL_POSITION</span></span>|<span data-ttu-id="34f90-196">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-196">Int32</span></span>|
|<span data-ttu-id="34f90-197">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="34f90-197">IS_NULLABLE</span></span>|<span data-ttu-id="34f90-198">String</span><span class="sxs-lookup"><span data-stu-id="34f90-198">String</span></span>|
|<span data-ttu-id="34f90-199">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="34f90-199">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="34f90-200">String</span><span class="sxs-lookup"><span data-stu-id="34f90-200">String</span></span>|
|<span data-ttu-id="34f90-201">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="34f90-201">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="34f90-202">String</span><span class="sxs-lookup"><span data-stu-id="34f90-202">String</span></span>|
|<span data-ttu-id="34f90-203">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-203">SS_DATA_TYPE</span></span>|<span data-ttu-id="34f90-204">Byte</span><span class="sxs-lookup"><span data-stu-id="34f90-204">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="34f90-205">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="34f90-205">Procedures</span></span>

|<span data-ttu-id="34f90-206">ColumnName</span><span class="sxs-lookup"><span data-stu-id="34f90-206">ColumnName</span></span>|<span data-ttu-id="34f90-207">DataType</span><span class="sxs-lookup"><span data-stu-id="34f90-207">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="34f90-208">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="34f90-208">PROCEDURE_CAT</span></span>|<span data-ttu-id="34f90-209">String</span><span class="sxs-lookup"><span data-stu-id="34f90-209">String</span></span>|
|<span data-ttu-id="34f90-210">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="34f90-210">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="34f90-211">String</span><span class="sxs-lookup"><span data-stu-id="34f90-211">String</span></span>|
|<span data-ttu-id="34f90-212">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-212">PROCEDURE_NAME</span></span>|<span data-ttu-id="34f90-213">String</span><span class="sxs-lookup"><span data-stu-id="34f90-213">String</span></span>|
|<span data-ttu-id="34f90-214">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="34f90-214">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="34f90-215">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-215">Int32</span></span>|
|<span data-ttu-id="34f90-216">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="34f90-216">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="34f90-217">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-217">Int32</span></span>|
|<span data-ttu-id="34f90-218">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="34f90-218">NUM_RESULT_SETS</span></span>|<span data-ttu-id="34f90-219">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-219">Int32</span></span>|
|<span data-ttu-id="34f90-220">COMENTARIOS</span><span class="sxs-lookup"><span data-stu-id="34f90-220">REMARKS</span></span>|<span data-ttu-id="34f90-221">String</span><span class="sxs-lookup"><span data-stu-id="34f90-221">String</span></span>|
|<span data-ttu-id="34f90-222">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-222">PROCEDURE_TYPE</span></span>|<span data-ttu-id="34f90-223">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-223">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="34f90-224">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="34f90-224">ProcedureColumns</span></span>

|<span data-ttu-id="34f90-225">ColumnName</span><span class="sxs-lookup"><span data-stu-id="34f90-225">ColumnName</span></span>|<span data-ttu-id="34f90-226">DataType</span><span class="sxs-lookup"><span data-stu-id="34f90-226">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="34f90-227">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="34f90-227">PROCEDURE_CAT</span></span>|<span data-ttu-id="34f90-228">String</span><span class="sxs-lookup"><span data-stu-id="34f90-228">String</span></span>|
|<span data-ttu-id="34f90-229">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="34f90-229">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="34f90-230">String</span><span class="sxs-lookup"><span data-stu-id="34f90-230">String</span></span>|
|<span data-ttu-id="34f90-231">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-231">PROCEDURE_NAME</span></span>|<span data-ttu-id="34f90-232">String</span><span class="sxs-lookup"><span data-stu-id="34f90-232">String</span></span>|
|<span data-ttu-id="34f90-233">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-233">COLUMN_NAME</span></span>|<span data-ttu-id="34f90-234">String</span><span class="sxs-lookup"><span data-stu-id="34f90-234">String</span></span>|
|<span data-ttu-id="34f90-235">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-235">COLUMN_TYPE</span></span>|<span data-ttu-id="34f90-236">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-236">Int16</span></span>|
|<span data-ttu-id="34f90-237">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-237">DATA_TYPE</span></span>|<span data-ttu-id="34f90-238">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-238">Int16</span></span>|
|<span data-ttu-id="34f90-239">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-239">TYPE_NAME</span></span>|<span data-ttu-id="34f90-240">String</span><span class="sxs-lookup"><span data-stu-id="34f90-240">String</span></span>|
|<span data-ttu-id="34f90-241">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="34f90-241">COLUMN_SIZE</span></span>|<span data-ttu-id="34f90-242">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-242">Int32</span></span>|
|<span data-ttu-id="34f90-243">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="34f90-243">BUFFER_LENGTH</span></span>|<span data-ttu-id="34f90-244">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-244">Int32</span></span>|
|<span data-ttu-id="34f90-245">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="34f90-245">DECIMAL_DIGITS</span></span>|<span data-ttu-id="34f90-246">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-246">Int16</span></span>|
|<span data-ttu-id="34f90-247">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="34f90-247">NUM_PREC_RADIX</span></span>|<span data-ttu-id="34f90-248">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-248">Int16</span></span>|
|<span data-ttu-id="34f90-249">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="34f90-249">NULLABLE</span></span>|<span data-ttu-id="34f90-250">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-250">Int16</span></span>|
|<span data-ttu-id="34f90-251">COMENTARIOS</span><span class="sxs-lookup"><span data-stu-id="34f90-251">REMARKS</span></span>|<span data-ttu-id="34f90-252">String</span><span class="sxs-lookup"><span data-stu-id="34f90-252">String</span></span>|
|<span data-ttu-id="34f90-253">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="34f90-253">COLUMN_DEF</span></span>|<span data-ttu-id="34f90-254">String</span><span class="sxs-lookup"><span data-stu-id="34f90-254">String</span></span>|
|<span data-ttu-id="34f90-255">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-255">SQL_DATA_TYPE</span></span>|<span data-ttu-id="34f90-256">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-256">Int16</span></span>|
|<span data-ttu-id="34f90-257">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="34f90-257">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="34f90-258">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-258">Int16</span></span>|
|<span data-ttu-id="34f90-259">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="34f90-259">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="34f90-260">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-260">Int32</span></span>|
|<span data-ttu-id="34f90-261">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="34f90-261">ORDINAL_POSITION</span></span>|<span data-ttu-id="34f90-262">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-262">Int32</span></span>|
|<span data-ttu-id="34f90-263">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="34f90-263">IS_NULLABLE</span></span>|<span data-ttu-id="34f90-264">String</span><span class="sxs-lookup"><span data-stu-id="34f90-264">String</span></span>|
|<span data-ttu-id="34f90-265">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="34f90-265">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="34f90-266">String</span><span class="sxs-lookup"><span data-stu-id="34f90-266">String</span></span>|
|<span data-ttu-id="34f90-267">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="34f90-267">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="34f90-268">String</span><span class="sxs-lookup"><span data-stu-id="34f90-268">String</span></span>|
|<span data-ttu-id="34f90-269">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-269">SS_DATA_TYPE</span></span>|<span data-ttu-id="34f90-270">Byte</span><span class="sxs-lookup"><span data-stu-id="34f90-270">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="34f90-271">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="34f90-271">ProcedureParameters</span></span>

|<span data-ttu-id="34f90-272">ColumnName</span><span class="sxs-lookup"><span data-stu-id="34f90-272">ColumnName</span></span>|<span data-ttu-id="34f90-273">DataType</span><span class="sxs-lookup"><span data-stu-id="34f90-273">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="34f90-274">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="34f90-274">PROCEDURE_CAT</span></span>|<span data-ttu-id="34f90-275">String</span><span class="sxs-lookup"><span data-stu-id="34f90-275">String</span></span>|
|<span data-ttu-id="34f90-276">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="34f90-276">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="34f90-277">String</span><span class="sxs-lookup"><span data-stu-id="34f90-277">String</span></span>|
|<span data-ttu-id="34f90-278">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-278">PROCEDURE_NAME</span></span>|<span data-ttu-id="34f90-279">String</span><span class="sxs-lookup"><span data-stu-id="34f90-279">String</span></span>|
|<span data-ttu-id="34f90-280">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-280">COLUMN_NAME</span></span>|<span data-ttu-id="34f90-281">String</span><span class="sxs-lookup"><span data-stu-id="34f90-281">String</span></span>|
|<span data-ttu-id="34f90-282">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-282">COLUMN_TYPE</span></span>|<span data-ttu-id="34f90-283">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-283">Int16</span></span>|
|<span data-ttu-id="34f90-284">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-284">DATA_TYPE</span></span>|<span data-ttu-id="34f90-285">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-285">Int16</span></span>|
|<span data-ttu-id="34f90-286">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-286">TYPE_NAME</span></span>|<span data-ttu-id="34f90-287">String</span><span class="sxs-lookup"><span data-stu-id="34f90-287">String</span></span>|
|<span data-ttu-id="34f90-288">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="34f90-288">COLUMN_SIZE</span></span>|<span data-ttu-id="34f90-289">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-289">Int32</span></span>|
|<span data-ttu-id="34f90-290">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="34f90-290">BUFFER_LENGTH</span></span>|<span data-ttu-id="34f90-291">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-291">Int32</span></span>|
|<span data-ttu-id="34f90-292">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="34f90-292">DECIMAL_DIGITS</span></span>|<span data-ttu-id="34f90-293">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-293">Int16</span></span>|
|<span data-ttu-id="34f90-294">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="34f90-294">NUM_PREC_RADIX</span></span>|<span data-ttu-id="34f90-295">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-295">Int16</span></span>|
|<span data-ttu-id="34f90-296">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="34f90-296">NULLABLE</span></span>|<span data-ttu-id="34f90-297">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-297">Int16</span></span>|
|<span data-ttu-id="34f90-298">COMENTARIOS</span><span class="sxs-lookup"><span data-stu-id="34f90-298">REMARKS</span></span>|<span data-ttu-id="34f90-299">String</span><span class="sxs-lookup"><span data-stu-id="34f90-299">String</span></span>|
|<span data-ttu-id="34f90-300">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="34f90-300">COLUMN_DEF</span></span>|<span data-ttu-id="34f90-301">String</span><span class="sxs-lookup"><span data-stu-id="34f90-301">String</span></span>|
|<span data-ttu-id="34f90-302">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-302">SQL_DATA_TYPE</span></span>|<span data-ttu-id="34f90-303">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-303">Int16</span></span>|
|<span data-ttu-id="34f90-304">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="34f90-304">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="34f90-305">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-305">Int16</span></span>|
|<span data-ttu-id="34f90-306">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="34f90-306">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="34f90-307">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-307">Int32</span></span>|
|<span data-ttu-id="34f90-308">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="34f90-308">ORDINAL_POSITION</span></span>|<span data-ttu-id="34f90-309">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-309">Int32</span></span>|
|<span data-ttu-id="34f90-310">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="34f90-310">IS_NULLABLE</span></span>|<span data-ttu-id="34f90-311">String</span><span class="sxs-lookup"><span data-stu-id="34f90-311">String</span></span>|
|<span data-ttu-id="34f90-312">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="34f90-312">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="34f90-313">String</span><span class="sxs-lookup"><span data-stu-id="34f90-313">String</span></span>|
|<span data-ttu-id="34f90-314">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="34f90-314">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="34f90-315">String</span><span class="sxs-lookup"><span data-stu-id="34f90-315">String</span></span>|
|<span data-ttu-id="34f90-316">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-316">SS_DATA_TYPE</span></span>|<span data-ttu-id="34f90-317">Byte</span><span class="sxs-lookup"><span data-stu-id="34f90-317">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="34f90-318">Controlador ODBC para Oracle de Microsoft</span><span class="sxs-lookup"><span data-stu-id="34f90-318">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="34f90-319">El controlador ODBC para Oracle de Microsoft SQL Server admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="34f90-319">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="34f90-320">Tablas</span><span class="sxs-lookup"><span data-stu-id="34f90-320">Tables</span></span>

- <span data-ttu-id="34f90-321">Columnas</span><span class="sxs-lookup"><span data-stu-id="34f90-321">Columns</span></span>

- <span data-ttu-id="34f90-322">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="34f90-322">Procedures</span></span>

- <span data-ttu-id="34f90-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="34f90-323">ProcedureColumns</span></span>

- <span data-ttu-id="34f90-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="34f90-324">ProcedureParameters</span></span>

- <span data-ttu-id="34f90-325">Vistas</span><span class="sxs-lookup"><span data-stu-id="34f90-325">Views</span></span>

- <span data-ttu-id="34f90-326">Índices</span><span class="sxs-lookup"><span data-stu-id="34f90-326">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="34f90-327">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="34f90-327">Tables and Views</span></span>

|<span data-ttu-id="34f90-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="34f90-328">ColumnName</span></span>|<span data-ttu-id="34f90-329">DataType</span><span class="sxs-lookup"><span data-stu-id="34f90-329">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="34f90-330">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="34f90-330">TABLE_QUALIFIER</span></span>|<span data-ttu-id="34f90-331">String</span><span class="sxs-lookup"><span data-stu-id="34f90-331">String</span></span>|
|<span data-ttu-id="34f90-332">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="34f90-332">TABLE_OWNER</span></span>|<span data-ttu-id="34f90-333">String</span><span class="sxs-lookup"><span data-stu-id="34f90-333">String</span></span>|
|<span data-ttu-id="34f90-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-334">TABLE_NAME</span></span>|<span data-ttu-id="34f90-335">String</span><span class="sxs-lookup"><span data-stu-id="34f90-335">String</span></span>|
|<span data-ttu-id="34f90-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-336">TABLE_TYPE</span></span>|<span data-ttu-id="34f90-337">String</span><span class="sxs-lookup"><span data-stu-id="34f90-337">String</span></span>|
|<span data-ttu-id="34f90-338">COMENTARIOS</span><span class="sxs-lookup"><span data-stu-id="34f90-338">REMARKS</span></span>|<span data-ttu-id="34f90-339">String</span><span class="sxs-lookup"><span data-stu-id="34f90-339">String</span></span>|

### <a name="columns"></a><span data-ttu-id="34f90-340">Columnas</span><span class="sxs-lookup"><span data-stu-id="34f90-340">Columns</span></span>

|<span data-ttu-id="34f90-341">ColumnName</span><span class="sxs-lookup"><span data-stu-id="34f90-341">ColumnName</span></span>|<span data-ttu-id="34f90-342">DataType</span><span class="sxs-lookup"><span data-stu-id="34f90-342">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="34f90-343">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="34f90-343">TABLE_QUALIFIER</span></span>|<span data-ttu-id="34f90-344">String</span><span class="sxs-lookup"><span data-stu-id="34f90-344">String</span></span>|
|<span data-ttu-id="34f90-345">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="34f90-345">TABLE_OWNER</span></span>|<span data-ttu-id="34f90-346">String</span><span class="sxs-lookup"><span data-stu-id="34f90-346">String</span></span>|
|<span data-ttu-id="34f90-347">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-347">TABLE_NAME</span></span>|<span data-ttu-id="34f90-348">String</span><span class="sxs-lookup"><span data-stu-id="34f90-348">String</span></span>|
|<span data-ttu-id="34f90-349">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-349">COLUMN_NAME</span></span>|<span data-ttu-id="34f90-350">String</span><span class="sxs-lookup"><span data-stu-id="34f90-350">String</span></span>|
|<span data-ttu-id="34f90-351">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-351">DATA_TYPE</span></span>|<span data-ttu-id="34f90-352">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-352">Int16</span></span>|
|<span data-ttu-id="34f90-353">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-353">TYPE_NAME</span></span>|<span data-ttu-id="34f90-354">String</span><span class="sxs-lookup"><span data-stu-id="34f90-354">String</span></span>|
|<span data-ttu-id="34f90-355">PRECISION</span><span class="sxs-lookup"><span data-stu-id="34f90-355">PRECISION</span></span>|<span data-ttu-id="34f90-356">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-356">Int32</span></span>|
|<span data-ttu-id="34f90-357">LENGTH</span><span class="sxs-lookup"><span data-stu-id="34f90-357">LENGTH</span></span>|<span data-ttu-id="34f90-358">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-358">Int32</span></span>|
|<span data-ttu-id="34f90-359">SCALE</span><span class="sxs-lookup"><span data-stu-id="34f90-359">SCALE</span></span>|<span data-ttu-id="34f90-360">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-360">Int16</span></span>|
|<span data-ttu-id="34f90-361">RADIX</span><span class="sxs-lookup"><span data-stu-id="34f90-361">RADIX</span></span>|<span data-ttu-id="34f90-362">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-362">Int16</span></span>|
|<span data-ttu-id="34f90-363">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="34f90-363">NULLABLE</span></span>|<span data-ttu-id="34f90-364">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-364">Int16</span></span>|
|<span data-ttu-id="34f90-365">COMENTARIOS</span><span class="sxs-lookup"><span data-stu-id="34f90-365">REMARKS</span></span>|<span data-ttu-id="34f90-366">String</span><span class="sxs-lookup"><span data-stu-id="34f90-366">String</span></span>|
|<span data-ttu-id="34f90-367">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="34f90-367">ORDINAL_POSITION</span></span>|<span data-ttu-id="34f90-368">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-368">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="34f90-369">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="34f90-369">Procedures</span></span>

|<span data-ttu-id="34f90-370">ColumnName</span><span class="sxs-lookup"><span data-stu-id="34f90-370">ColumnName</span></span>|<span data-ttu-id="34f90-371">DataType</span><span class="sxs-lookup"><span data-stu-id="34f90-371">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="34f90-372">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="34f90-372">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="34f90-373">String</span><span class="sxs-lookup"><span data-stu-id="34f90-373">String</span></span>|
|<span data-ttu-id="34f90-374">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="34f90-374">PROCEDURE_OWNER</span></span>|<span data-ttu-id="34f90-375">String</span><span class="sxs-lookup"><span data-stu-id="34f90-375">String</span></span>|
|<span data-ttu-id="34f90-376">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-376">PROCEDURE_NAME</span></span>|<span data-ttu-id="34f90-377">String</span><span class="sxs-lookup"><span data-stu-id="34f90-377">String</span></span>|
|<span data-ttu-id="34f90-378">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="34f90-378">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="34f90-379">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-379">Int16</span></span>|
|<span data-ttu-id="34f90-380">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="34f90-380">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="34f90-381">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-381">Int16</span></span>|
|<span data-ttu-id="34f90-382">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="34f90-382">NUM_RESULT_SETS</span></span>|<span data-ttu-id="34f90-383">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-383">Int16</span></span>|
|<span data-ttu-id="34f90-384">COMENTARIOS</span><span class="sxs-lookup"><span data-stu-id="34f90-384">REMARKS</span></span>|<span data-ttu-id="34f90-385">String</span><span class="sxs-lookup"><span data-stu-id="34f90-385">String</span></span>|
|<span data-ttu-id="34f90-386">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-386">PROCEDURE_TYPE</span></span>|<span data-ttu-id="34f90-387">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-387">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="34f90-388">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="34f90-388">ProcedureColumns</span></span>

|<span data-ttu-id="34f90-389">ColumnName</span><span class="sxs-lookup"><span data-stu-id="34f90-389">ColumnName</span></span>|<span data-ttu-id="34f90-390">DataType</span><span class="sxs-lookup"><span data-stu-id="34f90-390">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="34f90-391">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="34f90-391">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="34f90-392">String</span><span class="sxs-lookup"><span data-stu-id="34f90-392">String</span></span>|
|<span data-ttu-id="34f90-393">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="34f90-393">PROCEDURE_OWNER</span></span>|<span data-ttu-id="34f90-394">String</span><span class="sxs-lookup"><span data-stu-id="34f90-394">String</span></span>|
|<span data-ttu-id="34f90-395">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-395">PROCEDURE_NAME</span></span>|<span data-ttu-id="34f90-396">String</span><span class="sxs-lookup"><span data-stu-id="34f90-396">String</span></span>|
|<span data-ttu-id="34f90-397">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-397">COLUMN_NAME</span></span>|<span data-ttu-id="34f90-398">String</span><span class="sxs-lookup"><span data-stu-id="34f90-398">String</span></span>|
|<span data-ttu-id="34f90-399">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-399">COLUMN_TYPE</span></span>|<span data-ttu-id="34f90-400">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-400">Int16</span></span>|
|<span data-ttu-id="34f90-401">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-401">DATA_TYPE</span></span>|<span data-ttu-id="34f90-402">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-402">Int16</span></span>|
|<span data-ttu-id="34f90-403">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-403">TYPE_NAME</span></span>|<span data-ttu-id="34f90-404">String</span><span class="sxs-lookup"><span data-stu-id="34f90-404">String</span></span>|
|<span data-ttu-id="34f90-405">PRECISION</span><span class="sxs-lookup"><span data-stu-id="34f90-405">PRECISION</span></span>|<span data-ttu-id="34f90-406">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-406">Int32</span></span>|
|<span data-ttu-id="34f90-407">LENGTH</span><span class="sxs-lookup"><span data-stu-id="34f90-407">LENGTH</span></span>|<span data-ttu-id="34f90-408">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-408">Int32</span></span>|
|<span data-ttu-id="34f90-409">SCALE</span><span class="sxs-lookup"><span data-stu-id="34f90-409">SCALE</span></span>|<span data-ttu-id="34f90-410">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-410">Int16</span></span>|
|<span data-ttu-id="34f90-411">RADIX</span><span class="sxs-lookup"><span data-stu-id="34f90-411">RADIX</span></span>|<span data-ttu-id="34f90-412">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-412">Int16</span></span>|
|<span data-ttu-id="34f90-413">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="34f90-413">NULLABLE</span></span>|<span data-ttu-id="34f90-414">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-414">Int16</span></span>|
|<span data-ttu-id="34f90-415">COMENTARIOS</span><span class="sxs-lookup"><span data-stu-id="34f90-415">REMARKS</span></span>|<span data-ttu-id="34f90-416">String</span><span class="sxs-lookup"><span data-stu-id="34f90-416">String</span></span>|
|<span data-ttu-id="34f90-417">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="34f90-417">OVERLOAD</span></span>|<span data-ttu-id="34f90-418">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-418">Int32</span></span>|
|<span data-ttu-id="34f90-419">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="34f90-419">ORDINAL_POSITION</span></span>|<span data-ttu-id="34f90-420">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-420">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="34f90-421">Controlador ODBC de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="34f90-421">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="34f90-422">El controlador ODBC de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="34f90-422">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="34f90-423">Tablas</span><span class="sxs-lookup"><span data-stu-id="34f90-423">Tables</span></span>

- <span data-ttu-id="34f90-424">Índices</span><span class="sxs-lookup"><span data-stu-id="34f90-424">Indexes</span></span>

- <span data-ttu-id="34f90-425">Columnas</span><span class="sxs-lookup"><span data-stu-id="34f90-425">Columns</span></span>

- <span data-ttu-id="34f90-426">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="34f90-426">Procedures</span></span>

- <span data-ttu-id="34f90-427">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="34f90-427">ProcedureColumns</span></span>

- <span data-ttu-id="34f90-428">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="34f90-428">ProcedureParameters</span></span>

- <span data-ttu-id="34f90-429">Vistas</span><span class="sxs-lookup"><span data-stu-id="34f90-429">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="34f90-430">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="34f90-430">Tables and Views</span></span>

|<span data-ttu-id="34f90-431">ColumnName</span><span class="sxs-lookup"><span data-stu-id="34f90-431">ColumnName</span></span>|<span data-ttu-id="34f90-432">DataType</span><span class="sxs-lookup"><span data-stu-id="34f90-432">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="34f90-433">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="34f90-433">TABLE_QUALIFIER</span></span>|<span data-ttu-id="34f90-434">String</span><span class="sxs-lookup"><span data-stu-id="34f90-434">String</span></span>|
|<span data-ttu-id="34f90-435">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="34f90-435">TABLE_OWNER</span></span>|<span data-ttu-id="34f90-436">String</span><span class="sxs-lookup"><span data-stu-id="34f90-436">String</span></span>|
|<span data-ttu-id="34f90-437">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-437">TABLE_NAME</span></span>|<span data-ttu-id="34f90-438">String</span><span class="sxs-lookup"><span data-stu-id="34f90-438">String</span></span>|
|<span data-ttu-id="34f90-439">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-439">TABLE_TYPE</span></span>|<span data-ttu-id="34f90-440">String</span><span class="sxs-lookup"><span data-stu-id="34f90-440">String</span></span>|
|<span data-ttu-id="34f90-441">COMENTARIOS</span><span class="sxs-lookup"><span data-stu-id="34f90-441">REMARKS</span></span>|<span data-ttu-id="34f90-442">String</span><span class="sxs-lookup"><span data-stu-id="34f90-442">String</span></span>|

### <a name="columns"></a><span data-ttu-id="34f90-443">Columnas</span><span class="sxs-lookup"><span data-stu-id="34f90-443">Columns</span></span>

|<span data-ttu-id="34f90-444">ColumnName</span><span class="sxs-lookup"><span data-stu-id="34f90-444">ColumnName</span></span>|<span data-ttu-id="34f90-445">DataType</span><span class="sxs-lookup"><span data-stu-id="34f90-445">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="34f90-446">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="34f90-446">TABLE_QUALIFIER</span></span>|<span data-ttu-id="34f90-447">String</span><span class="sxs-lookup"><span data-stu-id="34f90-447">String</span></span>|
|<span data-ttu-id="34f90-448">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="34f90-448">TABLE_OWNER</span></span>|<span data-ttu-id="34f90-449">String</span><span class="sxs-lookup"><span data-stu-id="34f90-449">String</span></span>|
|<span data-ttu-id="34f90-450">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-450">TABLE_NAME</span></span>|<span data-ttu-id="34f90-451">String</span><span class="sxs-lookup"><span data-stu-id="34f90-451">String</span></span>|
|<span data-ttu-id="34f90-452">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-452">COLUMN_NAME</span></span>|<span data-ttu-id="34f90-453">String</span><span class="sxs-lookup"><span data-stu-id="34f90-453">String</span></span>|
|<span data-ttu-id="34f90-454">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-454">DATA_TYPE</span></span>|<span data-ttu-id="34f90-455">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-455">Int16</span></span>|
|<span data-ttu-id="34f90-456">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-456">TYPE_NAME</span></span>|<span data-ttu-id="34f90-457">String</span><span class="sxs-lookup"><span data-stu-id="34f90-457">String</span></span>|
|<span data-ttu-id="34f90-458">PRECISION</span><span class="sxs-lookup"><span data-stu-id="34f90-458">PRECISION</span></span>|<span data-ttu-id="34f90-459">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-459">Int32</span></span>|
|<span data-ttu-id="34f90-460">LENGTH</span><span class="sxs-lookup"><span data-stu-id="34f90-460">LENGTH</span></span>|<span data-ttu-id="34f90-461">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-461">Int32</span></span>|
|<span data-ttu-id="34f90-462">SCALE</span><span class="sxs-lookup"><span data-stu-id="34f90-462">SCALE</span></span>|<span data-ttu-id="34f90-463">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-463">Int16</span></span>|
|<span data-ttu-id="34f90-464">RADIX</span><span class="sxs-lookup"><span data-stu-id="34f90-464">RADIX</span></span>|<span data-ttu-id="34f90-465">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-465">Int16</span></span>|
|<span data-ttu-id="34f90-466">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="34f90-466">NULLABLE</span></span>|<span data-ttu-id="34f90-467">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-467">Int16</span></span>|
|<span data-ttu-id="34f90-468">COMENTARIOS</span><span class="sxs-lookup"><span data-stu-id="34f90-468">REMARKS</span></span>|<span data-ttu-id="34f90-469">String</span><span class="sxs-lookup"><span data-stu-id="34f90-469">String</span></span>|
|<span data-ttu-id="34f90-470">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="34f90-470">ORDINAL_POSITION</span></span>|<span data-ttu-id="34f90-471">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-471">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="34f90-472">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="34f90-472">Procedures</span></span>

|<span data-ttu-id="34f90-473">ColumnName</span><span class="sxs-lookup"><span data-stu-id="34f90-473">ColumnName</span></span>|<span data-ttu-id="34f90-474">DataType</span><span class="sxs-lookup"><span data-stu-id="34f90-474">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="34f90-475">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="34f90-475">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="34f90-476">String</span><span class="sxs-lookup"><span data-stu-id="34f90-476">String</span></span>|
|<span data-ttu-id="34f90-477">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="34f90-477">PROCEDURE_OWNER</span></span>|<span data-ttu-id="34f90-478">String</span><span class="sxs-lookup"><span data-stu-id="34f90-478">String</span></span>|
|<span data-ttu-id="34f90-479">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-479">PROCEDURE_NAME</span></span>|<span data-ttu-id="34f90-480">String</span><span class="sxs-lookup"><span data-stu-id="34f90-480">String</span></span>|
|<span data-ttu-id="34f90-481">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="34f90-481">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="34f90-482">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-482">Int16</span></span>|
|<span data-ttu-id="34f90-483">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="34f90-483">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="34f90-484">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-484">Int16</span></span>|
|<span data-ttu-id="34f90-485">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="34f90-485">NUM_RESULT_SETS</span></span>|<span data-ttu-id="34f90-486">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-486">Int16</span></span>|
|<span data-ttu-id="34f90-487">COMENTARIOS</span><span class="sxs-lookup"><span data-stu-id="34f90-487">REMARKS</span></span>|<span data-ttu-id="34f90-488">String</span><span class="sxs-lookup"><span data-stu-id="34f90-488">String</span></span>|
|<span data-ttu-id="34f90-489">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-489">PROCEDURE_TYPE</span></span>|<span data-ttu-id="34f90-490">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-490">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="34f90-491">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="34f90-491">ProcedureColumns</span></span>

|<span data-ttu-id="34f90-492">ColumnName</span><span class="sxs-lookup"><span data-stu-id="34f90-492">ColumnName</span></span>|<span data-ttu-id="34f90-493">DataType</span><span class="sxs-lookup"><span data-stu-id="34f90-493">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="34f90-494">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="34f90-494">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="34f90-495">String</span><span class="sxs-lookup"><span data-stu-id="34f90-495">String</span></span>|
|<span data-ttu-id="34f90-496">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="34f90-496">PROCEDURE_OWNER</span></span>|<span data-ttu-id="34f90-497">String</span><span class="sxs-lookup"><span data-stu-id="34f90-497">String</span></span>|
|<span data-ttu-id="34f90-498">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-498">PROCEDURE_NAME</span></span>|<span data-ttu-id="34f90-499">String</span><span class="sxs-lookup"><span data-stu-id="34f90-499">String</span></span>|
|<span data-ttu-id="34f90-500">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-500">COLUMN_NAME</span></span>|<span data-ttu-id="34f90-501">String</span><span class="sxs-lookup"><span data-stu-id="34f90-501">String</span></span>|
|<span data-ttu-id="34f90-502">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-502">COLUMN_TYPE</span></span>|<span data-ttu-id="34f90-503">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-503">Int16</span></span>|
|<span data-ttu-id="34f90-504">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-504">DATA_TYPE</span></span>|<span data-ttu-id="34f90-505">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-505">Int16</span></span>|
|<span data-ttu-id="34f90-506">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-506">TYPE_NAME</span></span>|<span data-ttu-id="34f90-507">String</span><span class="sxs-lookup"><span data-stu-id="34f90-507">String</span></span>|
|<span data-ttu-id="34f90-508">PRECISION</span><span class="sxs-lookup"><span data-stu-id="34f90-508">PRECISION</span></span>|<span data-ttu-id="34f90-509">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-509">Int32</span></span>|
|<span data-ttu-id="34f90-510">LENGTH</span><span class="sxs-lookup"><span data-stu-id="34f90-510">LENGTH</span></span>|<span data-ttu-id="34f90-511">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-511">Int32</span></span>|
|<span data-ttu-id="34f90-512">SCALE</span><span class="sxs-lookup"><span data-stu-id="34f90-512">SCALE</span></span>|<span data-ttu-id="34f90-513">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-513">Int16</span></span>|
|<span data-ttu-id="34f90-514">RADIX</span><span class="sxs-lookup"><span data-stu-id="34f90-514">RADIX</span></span>|<span data-ttu-id="34f90-515">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-515">Int16</span></span>|
|<span data-ttu-id="34f90-516">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="34f90-516">NULLABLE</span></span>|<span data-ttu-id="34f90-517">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-517">Int16</span></span>|
|<span data-ttu-id="34f90-518">COMENTARIOS</span><span class="sxs-lookup"><span data-stu-id="34f90-518">REMARKS</span></span>|<span data-ttu-id="34f90-519">String</span><span class="sxs-lookup"><span data-stu-id="34f90-519">String</span></span>|
|<span data-ttu-id="34f90-520">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="34f90-520">OVERLOAD</span></span>|<span data-ttu-id="34f90-521">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-521">Int32</span></span>|
|<span data-ttu-id="34f90-522">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="34f90-522">ORDINAL_POSITION</span></span>|<span data-ttu-id="34f90-523">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-523">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="34f90-524">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="34f90-524">ProcedureParameters</span></span>

|<span data-ttu-id="34f90-525">ColumnName</span><span class="sxs-lookup"><span data-stu-id="34f90-525">ColumnName</span></span>|<span data-ttu-id="34f90-526">DataType</span><span class="sxs-lookup"><span data-stu-id="34f90-526">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="34f90-527">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="34f90-527">PROCEDURE_CAT</span></span>|<span data-ttu-id="34f90-528">String</span><span class="sxs-lookup"><span data-stu-id="34f90-528">String</span></span>|
|<span data-ttu-id="34f90-529">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="34f90-529">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="34f90-530">String</span><span class="sxs-lookup"><span data-stu-id="34f90-530">String</span></span>|
|<span data-ttu-id="34f90-531">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-531">PROCEDURE_NAME</span></span>|<span data-ttu-id="34f90-532">String</span><span class="sxs-lookup"><span data-stu-id="34f90-532">String</span></span>|
|<span data-ttu-id="34f90-533">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-533">COLUMN_NAME</span></span>|<span data-ttu-id="34f90-534">String</span><span class="sxs-lookup"><span data-stu-id="34f90-534">String</span></span>|
|<span data-ttu-id="34f90-535">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-535">COLUMN_TYPE</span></span>|<span data-ttu-id="34f90-536">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-536">Int16</span></span>|
|<span data-ttu-id="34f90-537">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-537">DATA_TYPE</span></span>|<span data-ttu-id="34f90-538">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-538">Int16</span></span>|
|<span data-ttu-id="34f90-539">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="34f90-539">TYPE_NAME</span></span>|<span data-ttu-id="34f90-540">String</span><span class="sxs-lookup"><span data-stu-id="34f90-540">String</span></span>|
|<span data-ttu-id="34f90-541">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="34f90-541">COLUMN_SIZE</span></span>|<span data-ttu-id="34f90-542">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-542">Int32</span></span>|
|<span data-ttu-id="34f90-543">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="34f90-543">BUFFER_LENGTH</span></span>|<span data-ttu-id="34f90-544">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-544">Int32</span></span>|
|<span data-ttu-id="34f90-545">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="34f90-545">DECIMAL_DIGITS</span></span>|<span data-ttu-id="34f90-546">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-546">Int16</span></span>|
|<span data-ttu-id="34f90-547">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="34f90-547">NUM_PREC_RADIX</span></span>|<span data-ttu-id="34f90-548">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-548">Int16</span></span>|
|<span data-ttu-id="34f90-549">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="34f90-549">NULLABLE</span></span>|<span data-ttu-id="34f90-550">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-550">Int16</span></span>|
|<span data-ttu-id="34f90-551">COMENTARIOS</span><span class="sxs-lookup"><span data-stu-id="34f90-551">REMARKS</span></span>|<span data-ttu-id="34f90-552">String</span><span class="sxs-lookup"><span data-stu-id="34f90-552">String</span></span>|
|<span data-ttu-id="34f90-553">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="34f90-553">COLUMN_DEF</span></span>|<span data-ttu-id="34f90-554">String</span><span class="sxs-lookup"><span data-stu-id="34f90-554">String</span></span>|
|<span data-ttu-id="34f90-555">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="34f90-555">SQL_DATA_TYPE</span></span>|<span data-ttu-id="34f90-556">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-556">Int16</span></span>|
|<span data-ttu-id="34f90-557">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="34f90-557">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="34f90-558">Int16</span><span class="sxs-lookup"><span data-stu-id="34f90-558">Int16</span></span>|
|<span data-ttu-id="34f90-559">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="34f90-559">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="34f90-560">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-560">Int32</span></span>|
|<span data-ttu-id="34f90-561">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="34f90-561">ORDINAL_POSITION</span></span>|<span data-ttu-id="34f90-562">Int32</span><span class="sxs-lookup"><span data-stu-id="34f90-562">Int32</span></span>|
|<span data-ttu-id="34f90-563">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="34f90-563">IS_NULLABLE</span></span>|<span data-ttu-id="34f90-564">String</span><span class="sxs-lookup"><span data-stu-id="34f90-564">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="34f90-565">Vea también</span><span class="sxs-lookup"><span data-stu-id="34f90-565">See also</span></span>

- [<span data-ttu-id="34f90-566">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="34f90-566">ADO.NET Overview</span></span>](ado-net-overview.md)
