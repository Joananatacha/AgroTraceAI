<!DOCTYPE html>
<html lang="es" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard del Proyecto: AgroTrace AI</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    
    <!-- Chosen Palette: Calm & Professional (Shades of Green, Gray, and Off-White) -->
    <!-- Application Structure Plan: La aplicación está diseñada como un panel de control interactivo con una barra de navegación lateral fija (en escritorio) y un área de contenido principal desplazable. Esta estructura de "dashboard" fue elegida porque permite al usuario tener una visión global constante de las secciones del proyecto (a través de la navegación) mientras explora los detalles de una sección específica en el área principal. Facilita la navegación no lineal, permitiendo saltar directamente a "Costos" o "Cronograma" sin necesidad de desplazamiento secuencial, lo cual es ideal para un análisis rápido por parte de stakeholders. -->
    <!-- Visualization & Content Choices: 1. Objetivos: Gráficos de dona de Chart.js para presentar los KPIs de forma visualmente atractiva y fácil de entender. 2. Cronograma: Un gráfico de barras horizontales (Gantt) de Chart.js para mostrar la duración y superposición de las fases del proyecto. 3. Costos: Un gráfico de torta de Chart.js para ilustrar la distribución del presupuesto. 4. WBS y Stakeholders: Listas estructuradas y con estilo para una presentación clara de información cualitativa. Todas las visualizaciones están diseñadas para ser interactivas al pasar el cursor, proporcionando detalles adicionales a través de tooltips. Se evitó el uso de SVG y Mermaid JS, cumpliendo con los requisitos. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->

    <style>
        body { font-family: 'Inter', sans-serif; background-color: #f8fafc; }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 400px;
        }
        @media (min-width: 768px) {
            .chart-container { height: 350px; }
        }
    </style>
</head>
<body class="bg-slate-50">

<div class="flex">
    <!-- Sidebar Navigation -->
    <aside class="sticky top-0 h-screen bg-white shadow-lg w-64 hidden lg:flex flex-col">
        <div class="flex items-center justify-center h-20 border-b">
            <h1 class="text-2xl font-bold text-green-700">AgroTrace AI</h1>
        </div>
        <nav class="flex-1 px-4 py-8 space-y-2">
            <a href="#summary" class="flex items-center px-4 py-2 text-gray-700 hover:bg-green-50 hover:text-green-700 rounded-md">Resumen</a>
            <a href="#objectives" class="flex items-center px-4 py-2 text-gray-700 hover:bg-green-50 hover:text-green-700 rounded-md">Objetivos</a>
            <a href="#planning" class="flex items-center px-4 py-2 text-gray-700 hover:bg-green-50 hover:text-green-700 rounded-md">Planificación</a>
            <a href="#resources" class="flex items-center px-4 py-2 text-gray-700 hover:bg-green-50 hover:text-green-700 rounded-md">Recursos</a>
            <a href="#stakeholders" class="flex items-center px-4 py-2 text-gray-700 hover:bg-green-50 hover:text-green-700 rounded-md">Interesados</a>
        </nav>
    </aside>

    <!-- Main Content -->
    <div class="flex-1 flex flex-col">
        <header class="bg-white shadow-sm p-4 lg:hidden">
            <h1 class="text-xl font-bold text-green-700 text-center">AgroTrace AI</h1>
        </header>

        <main class="flex-1 p-6 md:p-10">
            
            <!-- Summary Section -->
            <section id="summary" class="mb-16">
                <h2 class="text-3xl font-bold text-gray-800 mb-6">Resumen del Proyecto</h2>
                <div class="grid md:grid-cols-2 gap-8">
                    <div class="bg-white p-6 rounded-lg shadow-md">
                        <h3 class="font-bold text-xl mb-3 text-red-700">Enunciado del Problema</h3>
                        <p class="text-gray-600">La industria de exportación de fruta chilena enfrenta desafíos críticos en trazabilidad, eficiencia logística y cumplimiento normativo, lo que limita su competitividad y genera pérdidas significativas.</p>
                    </div>
                    <div class="bg-white p-6 rounded-lg shadow-md">
                        <h3 class="font-bold text-xl mb-3 text-green-700">Nuestra Solución</h3>
                        <p class="text-gray-600">Una plataforma SaaS que utiliza IA y Blockchain para digitalizar y transparentar toda la cadena de suministro, desde el huerto hasta el consumidor, aumentando la confianza y la rentabilidad.</p>
                    </div>
                </div>
            </section>

            <!-- Objectives Section -->
            <section id="objectives" class="mb-16">
                <h2 class="text-3xl font-bold text-gray-800 mb-6">Objetivos y KPIs</h2>
                <p class="text-gray-600 mb-8 max-w-3xl">El proyecto busca alcanzar metas específicas y medibles para transformar la industria. Estos son los indicadores clave de éxito (KPIs) para nuestro Producto Mínimo Viable (MVP).</p>
                <div class="grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-4 gap-6">
                    <div class="bg-white p-6 rounded-lg shadow-md text-center">
                        <div class="chart-container mx-auto" style="height: 150px; max-width: 150px;"><canvas id="kpi1Chart"></canvas></div>
                        <h3 class="font-semibold mt-4">Reducción Tiempo Documental</h3>
                        <p class="text-2xl font-bold text-green-600">-30%</p>
                    </div>
                    <div class="bg-white p-6 rounded-lg shadow-md text-center">
                        <div class="chart-container mx-auto" style="height: 150px; max-width: 150px;"><canvas id="kpi2Chart"></canvas></div>
                        <h3 class="font-semibold mt-4">Disminución Pérdidas por Frío</h3>
                        <p class="text-2xl font-bold text-green-600">-15%</p>
                    </div>
                    <div class="bg-white p-6 rounded-lg shadow-md text-center">
                        <div class="chart-container mx-auto" style="height: 150px; max-width: 150px;"><canvas id="kpi3Chart"></canvas></div>
                        <h3 class="font-semibold mt-4">Trazabilidad con Blockchain</h3>
                        <p class="text-2xl font-bold text-green-600">100%</p>
                    </div>
                    <div class="bg-white p-6 rounded-lg shadow-md text-center">
                        <div class="chart-container mx-auto" style="height: 150px; max-width: 150px;"><canvas id="kpi4Chart"></canvas></div>
                        <h3 class="font-semibold mt-4">Acceso a Datos de Mercado</h3>
                        <p class="text-2xl font-bold text-green-600">+20%</p>
                    </div>
                </div>
            </section>
            
            <!-- Planning Section -->
            <section id="planning" class="mb-16">
                <h2 class="text-3xl font-bold text-gray-800 mb-6">Planificación del Proyecto</h2>
                <div class="grid lg:grid-cols-1 gap-8">
                    <div class="bg-white p-6 rounded-lg shadow-md">
                         <h3 class="font-bold text-xl mb-4 text-center">Cronograma de Actividades (26 Semanas)</h3>
                         <div class="chart-container" style="max-width: 900px; height: 400px;"><canvas id="ganttChart"></canvas></div>
                    </div>
                </div>
            </section>

            <!-- Resources Section -->
            <section id="resources" class="mb-16">
                 <h2 class="text-3xl font-bold text-gray-800 mb-6">Recursos del Proyecto</h2>
                 <div class="grid lg:grid-cols-2 gap-8">
                     <div class="bg-white p-6 rounded-lg shadow-md">
                        <h3 class="font-bold text-xl mb-4 text-center">Estimación de Costos (Total: $115,000 USD)</h3>
                        <div class="chart-container"><canvas id="costChart"></canvas></div>
                     </div>
                     <div class="bg-white p-6 rounded-lg shadow-md">
                         <h3 class="font-bold text-xl mb-4 text-center">Estructura del Equipo</h3>
                         <div class="space-y-4">
                            <div class="p-3 bg-slate-100 rounded-md">
                                <p class="font-bold">Product Owner</p>
                                <p class="text-sm text-gray-600">Define la visión y prioriza el backlog.</p>
                            </div>
                             <div class="p-3 bg-slate-100 rounded-md">
                                <p class="font-bold">Scrum Master</p>
                                <p class="text-sm text-gray-600">Facilita el proceso y elimina impedimentos.</p>
                            </div>
                             <div class="p-3 bg-slate-100 rounded-md">
                                <p class="font-bold">Development Team (3)</p>
                                <p class="text-sm text-gray-600">Desarrollan la plataforma (Frontend, Backend, IA).</p>
                            </div>
                             <div class="p-3 bg-slate-100 rounded-md">
                                <p class="font-bold">Consultor Blockchain</p>
                                <p class="text-sm text-gray-600">Experto en la implementación de la trazabilidad.</p>
                            </div>
                         </div>
                     </div>
                 </div>
            </section>

            <!-- Stakeholders Section -->
            <section id="stakeholders">
                 <h2 class="text-3xl font-bold text-gray-800 mb-6">Interesados Clave</h2>
                 <div class="bg-white p-6 rounded-lg shadow-md">
                    <div class="flex flex-wrap justify-center gap-3">
                        <span class="bg-blue-100 text-blue-800 text-sm font-medium px-3 py-1.5 rounded-full">Productores y Exportadores</span>
                        <span class="bg-green-100 text-green-800 text-sm font-medium px-3 py-1.5 rounded-full">Importadores y Retailers</span>
                        <span class="bg-purple-100 text-purple-800 text-sm font-medium px-3 py-1.5 rounded-full">Empresas de Logística</span>
                        <span class="bg-yellow-100 text-yellow-800 text-sm font-medium px-3 py-1.5 rounded-full">SAG y Aduanas</span>
                        <span class="bg-pink-100 text-pink-800 text-sm font-medium px-3 py-1.5 rounded-full">Consumidores Finales</span>
                        <span class="bg-gray-200 text-gray-800 text-sm font-medium px-3 py-1.5 rounded-full">Equipo de Desarrollo</span>
                        <span class="bg-indigo-100 text-indigo-800 text-sm font-medium px-3 py-1.5 rounded-full">Inversionistas y Alta Dirección</span>
                    </div>
                 </div>
            </section>
        </main>
    </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', () => {

    const chartTooltipOptions = {
        plugins: {
            tooltip: {
                callbacks: {
                    title: function(tooltipItems) {
                        const item = tooltipItems[0];
                        let label = item.chart.data.labels[item.dataIndex];
                        if (Array.isArray(label)) {
                          return label.join(' ');
                        } else {
                          return label;
                        }
                    }
                }
            }
        }
    };

    const kpiOptions = {
        responsive: true,
        maintainAspectRatio: false,
        cutout: '80%',
        plugins: { legend: { display: false }, tooltip: { enabled: false } }
    };

    new Chart('kpi1Chart', { type: 'doughnut', data: { datasets: [{ data: [30, 70], backgroundColor: ['#16a34a', '#e2e8f0'], borderWidth: 0 }] }, options: kpiOptions });
    new Chart('kpi2Chart', { type: 'doughnut', data: { datasets: [{ data: [15, 85], backgroundColor: ['#16a34a', '#e2e8f0'], borderWidth: 0 }] }, options: kpiOptions });
    new Chart('kpi3Chart', { type: 'doughnut', data: { datasets: [{ data: [100, 0], backgroundColor: ['#16a34a', '#e2e8f0'], borderWidth: 0 }] }, options: kpiOptions });
    new Chart('kpi4Chart', { type: 'doughnut', data: { datasets: [{ data: [20, 80], backgroundColor: ['#16a34a', '#e2e8f0'], borderWidth: 0 }] }, options: kpiOptions });
    
    const ganttLabels = [
        ['Cierre y', 'Monitoreo'], 
        ['Lanzamiento y', 'Capacitación'],
        ['Pruebas y', 'Validación'], 
        'Desarrollo del MVP', 
        ['Investigación y', 'Diseño']
    ];
    new Chart('ganttChart', {
        type: 'bar',
        data: {
            labels: ganttLabels,
            datasets: [{
                label: 'Semanas',
                data: [[25, 26], [21, 24], [17, 20], [5, 16], [1, 4]],
                backgroundColor: ['#ef4444', '#8b5cf6', '#f97316', '#16a34a', '#3b82f6'],
                borderWidth: 1,
                barPercentage: 0.6,
            }]
        },
        options: {
            ...chartTooltipOptions,
            indexAxis: 'y',
            responsive: true,
            maintainAspectRatio: false,
            plugins: { ...chartTooltipOptions.plugins, legend: { display: false } },
            scales: { x: { min: 0, max: 28, title: { display: true, text: 'Semanas del Proyecto' } } }
        }
    });

    const costLabels = [
        'Desarrollo de Software', 'Gestión de Proyecto', ['Consultoría', 'Blockchain'], 
        'Infraestructura', ['Capacitación y', 'Marketing'], 'Diseño UX/UI', 'Contingencia (15%)'
    ];
    new Chart('costChart', {
        type: 'pie',
        data: {
            labels: costLabels,
            datasets: [{
                data: [54000, 18000, 12000, 9000, 3000, 4000, 15000],
                backgroundColor: ['#15803d', '#16a34a', '#65a30d', '#a3e635', '#bef264', '#d9f99d', '#d1d5db'],
            }]
        },
        options: {
            ...chartTooltipOptions,
            responsive: true,
            maintainAspectRatio: false,
        }
    });
});
</script>

</body>
</html>
