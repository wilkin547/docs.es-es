---
title: Colecciones de esquemas de ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: f0240e99d2420b0956d3c144f837b39e094bb78a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794721"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="10262-102">Colecciones de esquemas de ODBC</span><span class="sxs-lookup"><span data-stu-id="10262-102">ODBC Schema Collections</span></span>

<span data-ttu-id="10262-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los controladores ODBC de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="10262-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="10262-104">Controlador ODBC para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="10262-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="10262-105">El controlador ODBC de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="10262-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="10262-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="10262-106">Tables</span></span>

- <span data-ttu-id="10262-107">Índices</span><span class="sxs-lookup"><span data-stu-id="10262-107">Indexes</span></span>

- <span data-ttu-id="10262-108">Columnas</span><span class="sxs-lookup"><span data-stu-id="10262-108">Columns</span></span>

- <span data-ttu-id="10262-109">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="10262-109">Procedures</span></span>

- <span data-ttu-id="10262-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="10262-110">ProcedureColumns</span></span>

- <span data-ttu-id="10262-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="10262-111">ProcedureParameters</span></span>

- <span data-ttu-id="10262-112">Vistas</span><span class="sxs-lookup"><span data-stu-id="10262-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="10262-113">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="10262-113">Tables and Views</span></span>

|<span data-ttu-id="10262-114">ColumName</span><span class="sxs-lookup"><span data-stu-id="10262-114">ColumnName</span></span>|<span data-ttu-id="10262-115">DataType</span><span class="sxs-lookup"><span data-stu-id="10262-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="10262-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="10262-116">TABLE_CAT</span></span>|<span data-ttu-id="10262-117">string</span><span class="sxs-lookup"><span data-stu-id="10262-117">String</span></span>|
|<span data-ttu-id="10262-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="10262-118">TABLE_SCHEM</span></span>|<span data-ttu-id="10262-119">string</span><span class="sxs-lookup"><span data-stu-id="10262-119">String</span></span>|
|<span data-ttu-id="10262-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-120">TABLE_NAME</span></span>|<span data-ttu-id="10262-121">string</span><span class="sxs-lookup"><span data-stu-id="10262-121">String</span></span>|
|<span data-ttu-id="10262-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-122">TABLE_TYPE</span></span>|<span data-ttu-id="10262-123">string</span><span class="sxs-lookup"><span data-stu-id="10262-123">String</span></span>|
|<span data-ttu-id="10262-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="10262-124">REMARKS</span></span>|<span data-ttu-id="10262-125">string</span><span class="sxs-lookup"><span data-stu-id="10262-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="10262-126">Índices</span><span class="sxs-lookup"><span data-stu-id="10262-126">Indexes</span></span>

|<span data-ttu-id="10262-127">ColumName</span><span class="sxs-lookup"><span data-stu-id="10262-127">ColumnName</span></span>|<span data-ttu-id="10262-128">DataType</span><span class="sxs-lookup"><span data-stu-id="10262-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="10262-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="10262-129">TABLE_CAT</span></span>|<span data-ttu-id="10262-130">string</span><span class="sxs-lookup"><span data-stu-id="10262-130">String</span></span>|
|<span data-ttu-id="10262-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="10262-131">TABLE_SCHEM</span></span>|<span data-ttu-id="10262-132">string</span><span class="sxs-lookup"><span data-stu-id="10262-132">String</span></span>|
|<span data-ttu-id="10262-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-133">TABLE_NAME</span></span>|<span data-ttu-id="10262-134">string</span><span class="sxs-lookup"><span data-stu-id="10262-134">String</span></span>|
|<span data-ttu-id="10262-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="10262-135">NON_UNIQUE</span></span>|<span data-ttu-id="10262-136">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-136">Int16</span></span>|
|<span data-ttu-id="10262-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="10262-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="10262-138">string</span><span class="sxs-lookup"><span data-stu-id="10262-138">String</span></span>|
|<span data-ttu-id="10262-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-139">INDEX_NAME</span></span>|<span data-ttu-id="10262-140">string</span><span class="sxs-lookup"><span data-stu-id="10262-140">String</span></span>|
|<span data-ttu-id="10262-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-141">TYPE</span></span>|<span data-ttu-id="10262-142">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-142">Int16</span></span>|
|<span data-ttu-id="10262-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="10262-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="10262-144">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-144">Int16</span></span>|
|<span data-ttu-id="10262-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-145">COLUMN_NAME</span></span>|<span data-ttu-id="10262-146">string</span><span class="sxs-lookup"><span data-stu-id="10262-146">String</span></span>|
|<span data-ttu-id="10262-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="10262-147">ASC_OR_DESC</span></span>|<span data-ttu-id="10262-148">string</span><span class="sxs-lookup"><span data-stu-id="10262-148">String</span></span>|
|<span data-ttu-id="10262-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="10262-149">CARDINALITY</span></span>|<span data-ttu-id="10262-150">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-150">Int32</span></span>|
|<span data-ttu-id="10262-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="10262-151">PAGES</span></span>|<span data-ttu-id="10262-152">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-152">Int32</span></span>|
|<span data-ttu-id="10262-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="10262-153">FILTER_CONDITION</span></span>|<span data-ttu-id="10262-154">string</span><span class="sxs-lookup"><span data-stu-id="10262-154">String</span></span>|
|<span data-ttu-id="10262-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10262-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="10262-156">string</span><span class="sxs-lookup"><span data-stu-id="10262-156">String</span></span>|
|<span data-ttu-id="10262-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="10262-158">Byte</span><span class="sxs-lookup"><span data-stu-id="10262-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="10262-159">Columnas</span><span class="sxs-lookup"><span data-stu-id="10262-159">Columns</span></span>

|<span data-ttu-id="10262-160">ColumName</span><span class="sxs-lookup"><span data-stu-id="10262-160">ColumnName</span></span>|<span data-ttu-id="10262-161">DataType</span><span class="sxs-lookup"><span data-stu-id="10262-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="10262-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="10262-162">TABLE_CAT</span></span>|<span data-ttu-id="10262-163">string</span><span class="sxs-lookup"><span data-stu-id="10262-163">String</span></span>|
|<span data-ttu-id="10262-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="10262-164">TABLE_SCHEM</span></span>|<span data-ttu-id="10262-165">string</span><span class="sxs-lookup"><span data-stu-id="10262-165">String</span></span>|
|<span data-ttu-id="10262-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-166">TABLE_NAME</span></span>|<span data-ttu-id="10262-167">string</span><span class="sxs-lookup"><span data-stu-id="10262-167">String</span></span>|
|<span data-ttu-id="10262-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-168">COLUMN_NAME</span></span>|<span data-ttu-id="10262-169">string</span><span class="sxs-lookup"><span data-stu-id="10262-169">String</span></span>|
|<span data-ttu-id="10262-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-170">DATA_TYPE</span></span>|<span data-ttu-id="10262-171">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-171">Int16</span></span>|
|<span data-ttu-id="10262-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-172">TYPE_NAME</span></span>|<span data-ttu-id="10262-173">string</span><span class="sxs-lookup"><span data-stu-id="10262-173">String</span></span>|
|<span data-ttu-id="10262-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="10262-174">COLUMN_SIZE</span></span>|<span data-ttu-id="10262-175">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-175">Int32</span></span>|
|<span data-ttu-id="10262-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10262-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="10262-177">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-177">Int32</span></span>|
|<span data-ttu-id="10262-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="10262-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="10262-179">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-179">Int16</span></span>|
|<span data-ttu-id="10262-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="10262-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="10262-181">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-181">Int16</span></span>|
|<span data-ttu-id="10262-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="10262-182">NULLABLE</span></span>|<span data-ttu-id="10262-183">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-183">Int16</span></span>|
|<span data-ttu-id="10262-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="10262-184">REMARKS</span></span>|<span data-ttu-id="10262-185">string</span><span class="sxs-lookup"><span data-stu-id="10262-185">String</span></span>|
|<span data-ttu-id="10262-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="10262-186">COLUMN_DEF</span></span>|<span data-ttu-id="10262-187">string</span><span class="sxs-lookup"><span data-stu-id="10262-187">String</span></span>|
|<span data-ttu-id="10262-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="10262-189">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-189">Int16</span></span>|
|<span data-ttu-id="10262-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="10262-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="10262-191">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-191">Int16</span></span>|
|<span data-ttu-id="10262-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10262-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="10262-193">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-193">Int32</span></span>|
|<span data-ttu-id="10262-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="10262-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="10262-195">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-195">Int32</span></span>|
|<span data-ttu-id="10262-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="10262-196">IS_NULLABLE</span></span>|<span data-ttu-id="10262-197">string</span><span class="sxs-lookup"><span data-stu-id="10262-197">String</span></span>|
|<span data-ttu-id="10262-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10262-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="10262-199">string</span><span class="sxs-lookup"><span data-stu-id="10262-199">String</span></span>|
|<span data-ttu-id="10262-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10262-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="10262-201">string</span><span class="sxs-lookup"><span data-stu-id="10262-201">String</span></span>|
|<span data-ttu-id="10262-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="10262-203">Byte</span><span class="sxs-lookup"><span data-stu-id="10262-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="10262-204">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="10262-204">Procedures</span></span>

|<span data-ttu-id="10262-205">ColumName</span><span class="sxs-lookup"><span data-stu-id="10262-205">ColumnName</span></span>|<span data-ttu-id="10262-206">DataType</span><span class="sxs-lookup"><span data-stu-id="10262-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="10262-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="10262-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="10262-208">string</span><span class="sxs-lookup"><span data-stu-id="10262-208">String</span></span>|
|<span data-ttu-id="10262-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="10262-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="10262-210">string</span><span class="sxs-lookup"><span data-stu-id="10262-210">String</span></span>|
|<span data-ttu-id="10262-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="10262-212">string</span><span class="sxs-lookup"><span data-stu-id="10262-212">String</span></span>|
|<span data-ttu-id="10262-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="10262-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="10262-214">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-214">Int32</span></span>|
|<span data-ttu-id="10262-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="10262-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="10262-216">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-216">Int32</span></span>|
|<span data-ttu-id="10262-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="10262-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="10262-218">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-218">Int32</span></span>|
|<span data-ttu-id="10262-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="10262-219">REMARKS</span></span>|<span data-ttu-id="10262-220">string</span><span class="sxs-lookup"><span data-stu-id="10262-220">String</span></span>|
|<span data-ttu-id="10262-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="10262-222">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="10262-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="10262-223">ProcedureColumns</span></span>

|<span data-ttu-id="10262-224">ColumName</span><span class="sxs-lookup"><span data-stu-id="10262-224">ColumnName</span></span>|<span data-ttu-id="10262-225">DataType</span><span class="sxs-lookup"><span data-stu-id="10262-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="10262-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="10262-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="10262-227">string</span><span class="sxs-lookup"><span data-stu-id="10262-227">String</span></span>|
|<span data-ttu-id="10262-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="10262-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="10262-229">string</span><span class="sxs-lookup"><span data-stu-id="10262-229">String</span></span>|
|<span data-ttu-id="10262-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="10262-231">string</span><span class="sxs-lookup"><span data-stu-id="10262-231">String</span></span>|
|<span data-ttu-id="10262-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-232">COLUMN_NAME</span></span>|<span data-ttu-id="10262-233">string</span><span class="sxs-lookup"><span data-stu-id="10262-233">String</span></span>|
|<span data-ttu-id="10262-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-234">COLUMN_TYPE</span></span>|<span data-ttu-id="10262-235">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-235">Int16</span></span>|
|<span data-ttu-id="10262-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-236">DATA_TYPE</span></span>|<span data-ttu-id="10262-237">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-237">Int16</span></span>|
|<span data-ttu-id="10262-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-238">TYPE_NAME</span></span>|<span data-ttu-id="10262-239">string</span><span class="sxs-lookup"><span data-stu-id="10262-239">String</span></span>|
|<span data-ttu-id="10262-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="10262-240">COLUMN_SIZE</span></span>|<span data-ttu-id="10262-241">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-241">Int32</span></span>|
|<span data-ttu-id="10262-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10262-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="10262-243">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-243">Int32</span></span>|
|<span data-ttu-id="10262-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="10262-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="10262-245">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-245">Int16</span></span>|
|<span data-ttu-id="10262-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="10262-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="10262-247">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-247">Int16</span></span>|
|<span data-ttu-id="10262-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="10262-248">NULLABLE</span></span>|<span data-ttu-id="10262-249">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-249">Int16</span></span>|
|<span data-ttu-id="10262-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="10262-250">REMARKS</span></span>|<span data-ttu-id="10262-251">string</span><span class="sxs-lookup"><span data-stu-id="10262-251">String</span></span>|
|<span data-ttu-id="10262-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="10262-252">COLUMN_DEF</span></span>|<span data-ttu-id="10262-253">string</span><span class="sxs-lookup"><span data-stu-id="10262-253">String</span></span>|
|<span data-ttu-id="10262-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="10262-255">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-255">Int16</span></span>|
|<span data-ttu-id="10262-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="10262-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="10262-257">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-257">Int16</span></span>|
|<span data-ttu-id="10262-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10262-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="10262-259">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-259">Int32</span></span>|
|<span data-ttu-id="10262-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="10262-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="10262-261">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-261">Int32</span></span>|
|<span data-ttu-id="10262-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="10262-262">IS_NULLABLE</span></span>|<span data-ttu-id="10262-263">string</span><span class="sxs-lookup"><span data-stu-id="10262-263">String</span></span>|
|<span data-ttu-id="10262-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10262-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="10262-265">string</span><span class="sxs-lookup"><span data-stu-id="10262-265">String</span></span>|
|<span data-ttu-id="10262-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10262-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="10262-267">string</span><span class="sxs-lookup"><span data-stu-id="10262-267">String</span></span>|
|<span data-ttu-id="10262-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="10262-269">Byte</span><span class="sxs-lookup"><span data-stu-id="10262-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="10262-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="10262-270">ProcedureParameters</span></span>

|<span data-ttu-id="10262-271">ColumName</span><span class="sxs-lookup"><span data-stu-id="10262-271">ColumnName</span></span>|<span data-ttu-id="10262-272">DataType</span><span class="sxs-lookup"><span data-stu-id="10262-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="10262-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="10262-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="10262-274">string</span><span class="sxs-lookup"><span data-stu-id="10262-274">String</span></span>|
|<span data-ttu-id="10262-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="10262-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="10262-276">string</span><span class="sxs-lookup"><span data-stu-id="10262-276">String</span></span>|
|<span data-ttu-id="10262-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="10262-278">string</span><span class="sxs-lookup"><span data-stu-id="10262-278">String</span></span>|
|<span data-ttu-id="10262-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-279">COLUMN_NAME</span></span>|<span data-ttu-id="10262-280">string</span><span class="sxs-lookup"><span data-stu-id="10262-280">String</span></span>|
|<span data-ttu-id="10262-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-281">COLUMN_TYPE</span></span>|<span data-ttu-id="10262-282">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-282">Int16</span></span>|
|<span data-ttu-id="10262-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-283">DATA_TYPE</span></span>|<span data-ttu-id="10262-284">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-284">Int16</span></span>|
|<span data-ttu-id="10262-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-285">TYPE_NAME</span></span>|<span data-ttu-id="10262-286">string</span><span class="sxs-lookup"><span data-stu-id="10262-286">String</span></span>|
|<span data-ttu-id="10262-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="10262-287">COLUMN_SIZE</span></span>|<span data-ttu-id="10262-288">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-288">Int32</span></span>|
|<span data-ttu-id="10262-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10262-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="10262-290">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-290">Int32</span></span>|
|<span data-ttu-id="10262-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="10262-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="10262-292">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-292">Int16</span></span>|
|<span data-ttu-id="10262-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="10262-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="10262-294">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-294">Int16</span></span>|
|<span data-ttu-id="10262-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="10262-295">NULLABLE</span></span>|<span data-ttu-id="10262-296">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-296">Int16</span></span>|
|<span data-ttu-id="10262-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="10262-297">REMARKS</span></span>|<span data-ttu-id="10262-298">string</span><span class="sxs-lookup"><span data-stu-id="10262-298">String</span></span>|
|<span data-ttu-id="10262-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="10262-299">COLUMN_DEF</span></span>|<span data-ttu-id="10262-300">string</span><span class="sxs-lookup"><span data-stu-id="10262-300">String</span></span>|
|<span data-ttu-id="10262-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="10262-302">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-302">Int16</span></span>|
|<span data-ttu-id="10262-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="10262-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="10262-304">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-304">Int16</span></span>|
|<span data-ttu-id="10262-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10262-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="10262-306">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-306">Int32</span></span>|
|<span data-ttu-id="10262-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="10262-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="10262-308">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-308">Int32</span></span>|
|<span data-ttu-id="10262-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="10262-309">IS_NULLABLE</span></span>|<span data-ttu-id="10262-310">string</span><span class="sxs-lookup"><span data-stu-id="10262-310">String</span></span>|
|<span data-ttu-id="10262-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10262-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="10262-312">string</span><span class="sxs-lookup"><span data-stu-id="10262-312">String</span></span>|
|<span data-ttu-id="10262-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10262-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="10262-314">string</span><span class="sxs-lookup"><span data-stu-id="10262-314">String</span></span>|
|<span data-ttu-id="10262-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="10262-316">Byte</span><span class="sxs-lookup"><span data-stu-id="10262-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="10262-317">Controlador ODBC para Oracle de Microsoft</span><span class="sxs-lookup"><span data-stu-id="10262-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="10262-318">El controlador ODBC de Oracle Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="10262-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="10262-319">Tablas</span><span class="sxs-lookup"><span data-stu-id="10262-319">Tables</span></span>

- <span data-ttu-id="10262-320">Columnas</span><span class="sxs-lookup"><span data-stu-id="10262-320">Columns</span></span>

- <span data-ttu-id="10262-321">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="10262-321">Procedures</span></span>

- <span data-ttu-id="10262-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="10262-322">ProcedureColumns</span></span>

- <span data-ttu-id="10262-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="10262-323">ProcedureParameters</span></span>

- <span data-ttu-id="10262-324">Vistas</span><span class="sxs-lookup"><span data-stu-id="10262-324">Views</span></span>

- <span data-ttu-id="10262-325">Índices</span><span class="sxs-lookup"><span data-stu-id="10262-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="10262-326">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="10262-326">Tables and Views</span></span>

|<span data-ttu-id="10262-327">ColumName</span><span class="sxs-lookup"><span data-stu-id="10262-327">ColumnName</span></span>|<span data-ttu-id="10262-328">DataType</span><span class="sxs-lookup"><span data-stu-id="10262-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="10262-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="10262-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="10262-330">string</span><span class="sxs-lookup"><span data-stu-id="10262-330">String</span></span>|
|<span data-ttu-id="10262-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="10262-331">TABLE_OWNER</span></span>|<span data-ttu-id="10262-332">string</span><span class="sxs-lookup"><span data-stu-id="10262-332">String</span></span>|
|<span data-ttu-id="10262-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-333">TABLE_NAME</span></span>|<span data-ttu-id="10262-334">string</span><span class="sxs-lookup"><span data-stu-id="10262-334">String</span></span>|
|<span data-ttu-id="10262-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-335">TABLE_TYPE</span></span>|<span data-ttu-id="10262-336">string</span><span class="sxs-lookup"><span data-stu-id="10262-336">String</span></span>|
|<span data-ttu-id="10262-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="10262-337">REMARKS</span></span>|<span data-ttu-id="10262-338">string</span><span class="sxs-lookup"><span data-stu-id="10262-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="10262-339">Columnas</span><span class="sxs-lookup"><span data-stu-id="10262-339">Columns</span></span>

|<span data-ttu-id="10262-340">ColumName</span><span class="sxs-lookup"><span data-stu-id="10262-340">ColumnName</span></span>|<span data-ttu-id="10262-341">DataType</span><span class="sxs-lookup"><span data-stu-id="10262-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="10262-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="10262-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="10262-343">string</span><span class="sxs-lookup"><span data-stu-id="10262-343">String</span></span>|
|<span data-ttu-id="10262-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="10262-344">TABLE_OWNER</span></span>|<span data-ttu-id="10262-345">string</span><span class="sxs-lookup"><span data-stu-id="10262-345">String</span></span>|
|<span data-ttu-id="10262-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-346">TABLE_NAME</span></span>|<span data-ttu-id="10262-347">string</span><span class="sxs-lookup"><span data-stu-id="10262-347">String</span></span>|
|<span data-ttu-id="10262-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-348">COLUMN_NAME</span></span>|<span data-ttu-id="10262-349">string</span><span class="sxs-lookup"><span data-stu-id="10262-349">String</span></span>|
|<span data-ttu-id="10262-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-350">DATA_TYPE</span></span>|<span data-ttu-id="10262-351">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-351">Int16</span></span>|
|<span data-ttu-id="10262-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-352">TYPE_NAME</span></span>|<span data-ttu-id="10262-353">string</span><span class="sxs-lookup"><span data-stu-id="10262-353">String</span></span>|
|<span data-ttu-id="10262-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="10262-354">PRECISION</span></span>|<span data-ttu-id="10262-355">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-355">Int32</span></span>|
|<span data-ttu-id="10262-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="10262-356">LENGTH</span></span>|<span data-ttu-id="10262-357">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-357">Int32</span></span>|
|<span data-ttu-id="10262-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="10262-358">SCALE</span></span>|<span data-ttu-id="10262-359">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-359">Int16</span></span>|
|<span data-ttu-id="10262-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="10262-360">RADIX</span></span>|<span data-ttu-id="10262-361">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-361">Int16</span></span>|
|<span data-ttu-id="10262-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="10262-362">NULLABLE</span></span>|<span data-ttu-id="10262-363">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-363">Int16</span></span>|
|<span data-ttu-id="10262-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="10262-364">REMARKS</span></span>|<span data-ttu-id="10262-365">string</span><span class="sxs-lookup"><span data-stu-id="10262-365">String</span></span>|
|<span data-ttu-id="10262-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="10262-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="10262-367">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="10262-368">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="10262-368">Procedures</span></span>

|<span data-ttu-id="10262-369">ColumName</span><span class="sxs-lookup"><span data-stu-id="10262-369">ColumnName</span></span>|<span data-ttu-id="10262-370">DataType</span><span class="sxs-lookup"><span data-stu-id="10262-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="10262-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="10262-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="10262-372">string</span><span class="sxs-lookup"><span data-stu-id="10262-372">String</span></span>|
|<span data-ttu-id="10262-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="10262-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="10262-374">string</span><span class="sxs-lookup"><span data-stu-id="10262-374">String</span></span>|
|<span data-ttu-id="10262-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="10262-376">string</span><span class="sxs-lookup"><span data-stu-id="10262-376">String</span></span>|
|<span data-ttu-id="10262-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="10262-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="10262-378">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-378">Int16</span></span>|
|<span data-ttu-id="10262-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="10262-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="10262-380">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-380">Int16</span></span>|
|<span data-ttu-id="10262-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="10262-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="10262-382">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-382">Int16</span></span>|
|<span data-ttu-id="10262-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="10262-383">REMARKS</span></span>|<span data-ttu-id="10262-384">string</span><span class="sxs-lookup"><span data-stu-id="10262-384">String</span></span>|
|<span data-ttu-id="10262-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="10262-386">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="10262-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="10262-387">ProcedureColumns</span></span>

|<span data-ttu-id="10262-388">ColumName</span><span class="sxs-lookup"><span data-stu-id="10262-388">ColumnName</span></span>|<span data-ttu-id="10262-389">DataType</span><span class="sxs-lookup"><span data-stu-id="10262-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="10262-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="10262-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="10262-391">string</span><span class="sxs-lookup"><span data-stu-id="10262-391">String</span></span>|
|<span data-ttu-id="10262-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="10262-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="10262-393">string</span><span class="sxs-lookup"><span data-stu-id="10262-393">String</span></span>|
|<span data-ttu-id="10262-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="10262-395">string</span><span class="sxs-lookup"><span data-stu-id="10262-395">String</span></span>|
|<span data-ttu-id="10262-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-396">COLUMN_NAME</span></span>|<span data-ttu-id="10262-397">string</span><span class="sxs-lookup"><span data-stu-id="10262-397">String</span></span>|
|<span data-ttu-id="10262-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-398">COLUMN_TYPE</span></span>|<span data-ttu-id="10262-399">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-399">Int16</span></span>|
|<span data-ttu-id="10262-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-400">DATA_TYPE</span></span>|<span data-ttu-id="10262-401">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-401">Int16</span></span>|
|<span data-ttu-id="10262-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-402">TYPE_NAME</span></span>|<span data-ttu-id="10262-403">string</span><span class="sxs-lookup"><span data-stu-id="10262-403">String</span></span>|
|<span data-ttu-id="10262-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="10262-404">PRECISION</span></span>|<span data-ttu-id="10262-405">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-405">Int32</span></span>|
|<span data-ttu-id="10262-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="10262-406">LENGTH</span></span>|<span data-ttu-id="10262-407">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-407">Int32</span></span>|
|<span data-ttu-id="10262-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="10262-408">SCALE</span></span>|<span data-ttu-id="10262-409">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-409">Int16</span></span>|
|<span data-ttu-id="10262-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="10262-410">RADIX</span></span>|<span data-ttu-id="10262-411">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-411">Int16</span></span>|
|<span data-ttu-id="10262-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="10262-412">NULLABLE</span></span>|<span data-ttu-id="10262-413">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-413">Int16</span></span>|
|<span data-ttu-id="10262-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="10262-414">REMARKS</span></span>|<span data-ttu-id="10262-415">string</span><span class="sxs-lookup"><span data-stu-id="10262-415">String</span></span>|
|<span data-ttu-id="10262-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="10262-416">OVERLOAD</span></span>|<span data-ttu-id="10262-417">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-417">Int32</span></span>|
|<span data-ttu-id="10262-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="10262-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="10262-419">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="10262-420">Controlador ODBC de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="10262-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="10262-421">El controlador ODBC de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="10262-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="10262-422">Tablas</span><span class="sxs-lookup"><span data-stu-id="10262-422">Tables</span></span>

- <span data-ttu-id="10262-423">Índices</span><span class="sxs-lookup"><span data-stu-id="10262-423">Indexes</span></span>

- <span data-ttu-id="10262-424">Columnas</span><span class="sxs-lookup"><span data-stu-id="10262-424">Columns</span></span>

- <span data-ttu-id="10262-425">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="10262-425">Procedures</span></span>

- <span data-ttu-id="10262-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="10262-426">ProcedureColumns</span></span>

- <span data-ttu-id="10262-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="10262-427">ProcedureParameters</span></span>

- <span data-ttu-id="10262-428">Vistas</span><span class="sxs-lookup"><span data-stu-id="10262-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="10262-429">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="10262-429">Tables and Views</span></span>

|<span data-ttu-id="10262-430">ColumName</span><span class="sxs-lookup"><span data-stu-id="10262-430">ColumnName</span></span>|<span data-ttu-id="10262-431">DataType</span><span class="sxs-lookup"><span data-stu-id="10262-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="10262-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="10262-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="10262-433">string</span><span class="sxs-lookup"><span data-stu-id="10262-433">String</span></span>|
|<span data-ttu-id="10262-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="10262-434">TABLE_OWNER</span></span>|<span data-ttu-id="10262-435">string</span><span class="sxs-lookup"><span data-stu-id="10262-435">String</span></span>|
|<span data-ttu-id="10262-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-436">TABLE_NAME</span></span>|<span data-ttu-id="10262-437">string</span><span class="sxs-lookup"><span data-stu-id="10262-437">String</span></span>|
|<span data-ttu-id="10262-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-438">TABLE_TYPE</span></span>|<span data-ttu-id="10262-439">string</span><span class="sxs-lookup"><span data-stu-id="10262-439">String</span></span>|
|<span data-ttu-id="10262-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="10262-440">REMARKS</span></span>|<span data-ttu-id="10262-441">string</span><span class="sxs-lookup"><span data-stu-id="10262-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="10262-442">Columnas</span><span class="sxs-lookup"><span data-stu-id="10262-442">Columns</span></span>

|<span data-ttu-id="10262-443">ColumName</span><span class="sxs-lookup"><span data-stu-id="10262-443">ColumnName</span></span>|<span data-ttu-id="10262-444">DataType</span><span class="sxs-lookup"><span data-stu-id="10262-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="10262-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="10262-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="10262-446">string</span><span class="sxs-lookup"><span data-stu-id="10262-446">String</span></span>|
|<span data-ttu-id="10262-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="10262-447">TABLE_OWNER</span></span>|<span data-ttu-id="10262-448">string</span><span class="sxs-lookup"><span data-stu-id="10262-448">String</span></span>|
|<span data-ttu-id="10262-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-449">TABLE_NAME</span></span>|<span data-ttu-id="10262-450">string</span><span class="sxs-lookup"><span data-stu-id="10262-450">String</span></span>|
|<span data-ttu-id="10262-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-451">COLUMN_NAME</span></span>|<span data-ttu-id="10262-452">string</span><span class="sxs-lookup"><span data-stu-id="10262-452">String</span></span>|
|<span data-ttu-id="10262-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-453">DATA_TYPE</span></span>|<span data-ttu-id="10262-454">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-454">Int16</span></span>|
|<span data-ttu-id="10262-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-455">TYPE_NAME</span></span>|<span data-ttu-id="10262-456">string</span><span class="sxs-lookup"><span data-stu-id="10262-456">String</span></span>|
|<span data-ttu-id="10262-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="10262-457">PRECISION</span></span>|<span data-ttu-id="10262-458">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-458">Int32</span></span>|
|<span data-ttu-id="10262-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="10262-459">LENGTH</span></span>|<span data-ttu-id="10262-460">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-460">Int32</span></span>|
|<span data-ttu-id="10262-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="10262-461">SCALE</span></span>|<span data-ttu-id="10262-462">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-462">Int16</span></span>|
|<span data-ttu-id="10262-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="10262-463">RADIX</span></span>|<span data-ttu-id="10262-464">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-464">Int16</span></span>|
|<span data-ttu-id="10262-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="10262-465">NULLABLE</span></span>|<span data-ttu-id="10262-466">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-466">Int16</span></span>|
|<span data-ttu-id="10262-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="10262-467">REMARKS</span></span>|<span data-ttu-id="10262-468">string</span><span class="sxs-lookup"><span data-stu-id="10262-468">String</span></span>|
|<span data-ttu-id="10262-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="10262-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="10262-470">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="10262-471">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="10262-471">Procedures</span></span>

|<span data-ttu-id="10262-472">ColumName</span><span class="sxs-lookup"><span data-stu-id="10262-472">ColumnName</span></span>|<span data-ttu-id="10262-473">DataType</span><span class="sxs-lookup"><span data-stu-id="10262-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="10262-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="10262-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="10262-475">string</span><span class="sxs-lookup"><span data-stu-id="10262-475">String</span></span>|
|<span data-ttu-id="10262-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="10262-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="10262-477">string</span><span class="sxs-lookup"><span data-stu-id="10262-477">String</span></span>|
|<span data-ttu-id="10262-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="10262-479">string</span><span class="sxs-lookup"><span data-stu-id="10262-479">String</span></span>|
|<span data-ttu-id="10262-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="10262-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="10262-481">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-481">Int16</span></span>|
|<span data-ttu-id="10262-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="10262-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="10262-483">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-483">Int16</span></span>|
|<span data-ttu-id="10262-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="10262-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="10262-485">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-485">Int16</span></span>|
|<span data-ttu-id="10262-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="10262-486">REMARKS</span></span>|<span data-ttu-id="10262-487">string</span><span class="sxs-lookup"><span data-stu-id="10262-487">String</span></span>|
|<span data-ttu-id="10262-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="10262-489">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="10262-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="10262-490">ProcedureColumns</span></span>

|<span data-ttu-id="10262-491">ColumName</span><span class="sxs-lookup"><span data-stu-id="10262-491">ColumnName</span></span>|<span data-ttu-id="10262-492">DataType</span><span class="sxs-lookup"><span data-stu-id="10262-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="10262-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="10262-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="10262-494">string</span><span class="sxs-lookup"><span data-stu-id="10262-494">String</span></span>|
|<span data-ttu-id="10262-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="10262-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="10262-496">string</span><span class="sxs-lookup"><span data-stu-id="10262-496">String</span></span>|
|<span data-ttu-id="10262-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="10262-498">string</span><span class="sxs-lookup"><span data-stu-id="10262-498">String</span></span>|
|<span data-ttu-id="10262-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-499">COLUMN_NAME</span></span>|<span data-ttu-id="10262-500">string</span><span class="sxs-lookup"><span data-stu-id="10262-500">String</span></span>|
|<span data-ttu-id="10262-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-501">COLUMN_TYPE</span></span>|<span data-ttu-id="10262-502">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-502">Int16</span></span>|
|<span data-ttu-id="10262-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-503">DATA_TYPE</span></span>|<span data-ttu-id="10262-504">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-504">Int16</span></span>|
|<span data-ttu-id="10262-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-505">TYPE_NAME</span></span>|<span data-ttu-id="10262-506">string</span><span class="sxs-lookup"><span data-stu-id="10262-506">String</span></span>|
|<span data-ttu-id="10262-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="10262-507">PRECISION</span></span>|<span data-ttu-id="10262-508">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-508">Int32</span></span>|
|<span data-ttu-id="10262-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="10262-509">LENGTH</span></span>|<span data-ttu-id="10262-510">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-510">Int32</span></span>|
|<span data-ttu-id="10262-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="10262-511">SCALE</span></span>|<span data-ttu-id="10262-512">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-512">Int16</span></span>|
|<span data-ttu-id="10262-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="10262-513">RADIX</span></span>|<span data-ttu-id="10262-514">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-514">Int16</span></span>|
|<span data-ttu-id="10262-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="10262-515">NULLABLE</span></span>|<span data-ttu-id="10262-516">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-516">Int16</span></span>|
|<span data-ttu-id="10262-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="10262-517">REMARKS</span></span>|<span data-ttu-id="10262-518">string</span><span class="sxs-lookup"><span data-stu-id="10262-518">String</span></span>|
|<span data-ttu-id="10262-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="10262-519">OVERLOAD</span></span>|<span data-ttu-id="10262-520">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-520">Int32</span></span>|
|<span data-ttu-id="10262-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="10262-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="10262-522">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="10262-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="10262-523">ProcedureParameters</span></span>

|<span data-ttu-id="10262-524">ColumName</span><span class="sxs-lookup"><span data-stu-id="10262-524">ColumnName</span></span>|<span data-ttu-id="10262-525">DataType</span><span class="sxs-lookup"><span data-stu-id="10262-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="10262-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="10262-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="10262-527">string</span><span class="sxs-lookup"><span data-stu-id="10262-527">String</span></span>|
|<span data-ttu-id="10262-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="10262-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="10262-529">string</span><span class="sxs-lookup"><span data-stu-id="10262-529">String</span></span>|
|<span data-ttu-id="10262-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="10262-531">string</span><span class="sxs-lookup"><span data-stu-id="10262-531">String</span></span>|
|<span data-ttu-id="10262-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-532">COLUMN_NAME</span></span>|<span data-ttu-id="10262-533">string</span><span class="sxs-lookup"><span data-stu-id="10262-533">String</span></span>|
|<span data-ttu-id="10262-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-534">COLUMN_TYPE</span></span>|<span data-ttu-id="10262-535">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-535">Int16</span></span>|
|<span data-ttu-id="10262-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-536">DATA_TYPE</span></span>|<span data-ttu-id="10262-537">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-537">Int16</span></span>|
|<span data-ttu-id="10262-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="10262-538">TYPE_NAME</span></span>|<span data-ttu-id="10262-539">string</span><span class="sxs-lookup"><span data-stu-id="10262-539">String</span></span>|
|<span data-ttu-id="10262-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="10262-540">COLUMN_SIZE</span></span>|<span data-ttu-id="10262-541">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-541">Int32</span></span>|
|<span data-ttu-id="10262-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10262-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="10262-543">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-543">Int32</span></span>|
|<span data-ttu-id="10262-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="10262-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="10262-545">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-545">Int16</span></span>|
|<span data-ttu-id="10262-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="10262-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="10262-547">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-547">Int16</span></span>|
|<span data-ttu-id="10262-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="10262-548">NULLABLE</span></span>|<span data-ttu-id="10262-549">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-549">Int16</span></span>|
|<span data-ttu-id="10262-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="10262-550">REMARKS</span></span>|<span data-ttu-id="10262-551">string</span><span class="sxs-lookup"><span data-stu-id="10262-551">String</span></span>|
|<span data-ttu-id="10262-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="10262-552">COLUMN_DEF</span></span>|<span data-ttu-id="10262-553">string</span><span class="sxs-lookup"><span data-stu-id="10262-553">String</span></span>|
|<span data-ttu-id="10262-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10262-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="10262-555">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-555">Int16</span></span>|
|<span data-ttu-id="10262-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="10262-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="10262-557">Int16</span><span class="sxs-lookup"><span data-stu-id="10262-557">Int16</span></span>|
|<span data-ttu-id="10262-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10262-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="10262-559">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-559">Int32</span></span>|
|<span data-ttu-id="10262-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="10262-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="10262-561">Int32</span><span class="sxs-lookup"><span data-stu-id="10262-561">Int32</span></span>|
|<span data-ttu-id="10262-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="10262-562">IS_NULLABLE</span></span>|<span data-ttu-id="10262-563">string</span><span class="sxs-lookup"><span data-stu-id="10262-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="10262-564">Vea también</span><span class="sxs-lookup"><span data-stu-id="10262-564">See also</span></span>

- [<span data-ttu-id="10262-565">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="10262-565">ADO.NET Overview</span></span>](ado-net-overview.md)
