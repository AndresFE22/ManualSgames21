<template>
    <v-app>
        
        <v-app-bar app v-if="this.$vuetify.breakpoint.mdAndDown">
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Manual de Usuario</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-img
        src="@/assets/logosgames21-removebg-preview.png"
        class="logo"
        max-width="50"
      ></v-img>
    </v-app-bar>
      <v-navigation-drawer v-if="this.$vuetify.breakpoint.mdAndDown"
      v-model="drawer"
      app
      fixed
      clipped
      class="custom-drawer"
      style="background-color: #121827;"
    >
      <!-- Logo o ícono en la parte superior -->
      <v-list-item class="logo-item">
        <v-list-item-content>
          <v-img
            src="@/assets/logosgamesblanco.png"
            class="logo"
            contain
          ></v-img>
        </v-list-item-content>
      </v-list-item>
  
      <!-- Lista de elementos del menú -->
      <v-list dense>
        <v-list-item-group v-model="selectedSection">
          <v-list-item
            v-for="(section, index) in sections"
            :key="index"
            @click="scrollToSection(section.id)"
            class="list-item"
          >
            <v-list-item-content>
              <v-list-item-title class="titlenavi">{{ section.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>



    <v-navigation-drawer
      app
      fixed
      clipped
      class="custom-drawer"
      style="background-color: #121827;"
    >
      <!-- Logo o ícono en la parte superior -->
      <v-list-item class="logo-item">
        <v-list-item-content>
          <v-img
            src="@/assets/logosgamesblanco.png"
            class="logo"
            contain
          ></v-img>
        </v-list-item-content>
      </v-list-item>
  
      <!-- Lista de elementos del menú -->
      <v-list dense>
        <v-list-item-group v-model="selectedSection">
          <v-list-item
            v-for="(section, index) in sections"
            :key="index"
            @click="scrollToSection(section.id)"
            class="list-item"
          >
            <v-list-item-content>
              <v-list-item-title class="titlenavi">{{ section.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

      <v-main class="main" style="margin: 0;">
        <v-container >
          <div v-for="(section, index) in sections" :key="index" :id="section.id">
            <div class="section-title">
              <h2>{{ section.title }}</h2>
            </div>
            <div class="section">
              <p v-html="section.content"></p>
            </div>
  
                  </div>
        </v-container>
        <v-footer class="d-flex flex-column pa-4" style="background-color: #121827;">
    <div class="bg-teal d-flex flex-column align-center py-4">
     <h3 style="color: white; font-family: 'Answer', sans-serif;">
        <strong>Manual de usuario para docentes de la plataforma SGames21</strong>
     </h3> 
      <a href="https://admin.sgames21.ai" target="_blank">admin.sgames21.ai</a>
      <v-divider class="my-4"></v-divider>
      <div class="text-center">
        <p style="color: white;">Presentado por: <strong>Lina Quitian Gómez</strong></p>
        <p style="color: white;">Revisado por: <strong>Juan Carlos Giraldo Cardozo</strong></p>
        <p style="color: white;">Aprobado por: <strong>Manuel Caro Piñeres</strong> </p>
      </div>
      <v-divider class="my-4"></v-divider>
      <div class="d-flex justify-center">
        <v-btn
          v-for="icon in icons"
          :key="icon"
          :icon="icon"
          class="mx-2"
          size="small"
          variant="plain"
        ></v-btn>
      </div>
    </div>
  </v-footer>
      </v-main>
    </v-app>
  </template>
  <script>
  export default {
    data() {
      return {
        drawer: false,
        selectedSection: null,
        sections: [
        {
    id: 'introduccion',
    title: 'Introducción',
    content: `<br>
      <p class="into">En el presente manual de usuario de la plataforma SGames21 dirigida a docentes de educación media en el departamento de Córdoba.Esta herramienta ha sido diseñada para brindar a los educadores de nuestra región una plataforma eficiente y poderosa que les permitirá crear y gestionar cursos en línea destinados a estudiantes de educación media, enriqueciendo así la experiencia educativa a través del aprendizaje digital y la asistencia de un módulo tutor.<br><br>
      En un mundo en constante evolución, la educación en línea se ha convertido en una herramienta esencial para la enseñanza y el aprendizaje, y esta plataforma está diseñada específicamente para adaptarse a las necesidades de los docentes y estudiantes de Córdoba.Aquí encontrarás todas las herramientas necesarias para diseñar, administrar y enriquecer las historias, brindando a tus estudiantes una experiencia educativa de alta calidad que se ajusta a las necesidades individuales.<br><br>
      A lo largo de este manual, te guiaremos a través de todas las funciones y características de la plataforma, desde la creación de mecánicas de juegos hasta la creación de historias.
      Esperamos que esta guía te ayude a aprovechar al máximo esta herramienta y a ofrecer una educación de excelencia a los jóvenes de nuestro departamento.<br><br>
      ¡Comencemos a explorar juntos la plataforma SGames21 para Docentes de educación media en el departamento de Córdoba y a transformar la forma en que enseñamos y aprendemos en la era digital!</p>
    `,
    
  
  }
  ,
          { id: 'requisitos', title: 'Requisitos del sistema', content: `<br> <p>Los requisitos con los que debe contar para poder ingresar a la plataforma SGames21, son los siguientes:</p>
  <ul>
    <li><strong>Hardware:</strong> contar con un dispositivo electrónico (celular, Tablet o computador), con un procesador de al menos 2GHz, 4GB de RAM, 1 GB de espacio en disco duro.</li>
    <li><strong>Software:</strong> contar con un sistema operativo compatible con el dispositivo electrónico como Windows, macOS, Linux, Android, iOS. También un navegador compatible como Chrome, Firefox, Safari, etc.</li>
    <li><strong>Conexión a internet:</strong> Contar con una conexión de banda ancha con una velocidad de descarga de al menos 3-5 Mbps y una velocidad de carga de al menos 1-2 Mbps, mediante datos móviles o WIFI.</li>
  </ul>` },
  
          { id: 'registro', title: 'Registro y acceso del usuario', content: `<br> <p>Para hacer el registro, debe primero ingresar al siguiente enlace: <a href="http://admin.sgames21.ai" target="_blank">admin.sgames21.ai</a>. Para comenzar el registro, lo primero que se debe hacer es dar clic en el botón que aparece en la <strong>Imagen 1</strong>.</p>
  
  <p><img src="${require('@/assets/registro1.jpg')}" alt="Registro de usuario" class="grande" /> 
            <div class="image-caption">
            Imagen 1: Registro de usuario
            </div>
            </p>
  
  <p>En la <strong>Imagen 2</strong>, se muestra el formulario del registro de usuario a la plataforma SGames21.</p>
  
  <p><img src="${require('@/assets/registro2.jpg')}" alt="Formulario de registro de usuario" />
              <div class="image-caption">
            Imagen 2: Formulario de registro de usuario
            </div></p>
  
  <p>El usuario estudiante debe ingresar la información como usuario o email, la contraseña, confirmar contraseña, la fecha de nacimiento del estudiante. Al final, debe dar clic en el botón “Aceptar”, para terminar el registro del usuario, como aparece en la <strong>Imagen 3</strong>.</p>
  
  <p><img src="${require('@/assets/registro3.jpg')}" alt="Registro de usuario" />
              <div class="image-caption">
            Imagen 3: Registro de usuario
            </div></p>
  
  <p>La <strong>Imagen 4</strong> muestra la vista de la página principal. Solo debe dar clic en el botón “INICIAR SESIÓN” como se muestra en la imagen.</p>
  
  <p><img src="${require('@/assets/registro4.jpg')}" alt="Inicio de sesión" />
              <div class="image-caption">
            Imagen 4: Inicio de sesión
            </div></p>
  
  <p>La <strong>Imagen 5</strong> muestra el formulario para ingresar a la plataforma. El usuario debe ingresar el correo electrónico, la contraseña y luego dar clic en “INICIAR SESIÓN”.</p>
  
  <p><img src="${require('@/assets/registro5.jpg')}" alt="Ingreso del usuario" />
              <div class="image-caption">
            Imagen 5: Ingreso del usuario
            </div></p>`},
  
          { id: 'interfaz', title: 'Interfaz de usuario', content: `<p>Cuando el usuario realiza el ingreso a la plataforma SGames21, lo que encuentra es su panel de administración como se muestra en la <strong>Imagen 6</strong>. A continuación se especifican cada uno de los puntos subrayados en rojo que hacen parte del panel de administración:</p>
  
  <ol>
    <li><strong>Inicio:</strong> Lugar de trabajo.</li>
    <li><strong>Crear y/o actualizar historias:</strong> Espacio para crear o actualizar las historias previamente creadas con los retos, fases, actividades y minijuegos.</li>
    <li><strong>Crear y/o actualizar mecánicas:</strong> Espacio para crear o actualizar las mecánicas de juego previamente creadas con el título y las fases.</li>
    <li><strong>Crear y/o actualizar cursos:</strong> Espacio para crear o actualizar los cursos.</li>
    <li><strong>Datos básicos del usuario:</strong> Espacio para editar o agregar información básica del usuario, como nombres, apellidos, fecha de nacimiento, contraseña, etc.</li>
  </ol>
  
  <p><img src="${require('@/assets/panel.png')}" alt="Panel de administración" />
     <div class="image-caption">
  Imagen 6: Panel de administración          </div> </p>` },
          {
            id: 'creacion',
            title: 'Creación de contenido',
          },
          { id: 'crearMecanica', title: 'Crear mecánica', content: `<br> <p>Antes de empezar a crear una mecánica de juego, es indispensable que entienda el concepto de mecánica de juego, esto con el objetivo de entender para qué se crea y el propósito de cada mecánica de juego.</p>
  
  <p>Una mecánica de juego está compuesta por una competencia de aprendizaje, esta es la capacidad de utilizar los conocimientos, habilidades, actitudes y valores que se adquieren o desarrollan en los procesos educativos para resolver problemas y situaciones de la vida cotidiana, personal, profesional y social. El aprendizaje por competencias implica que el estudiante sea activo, reflexivo, crítico y creativo en su proceso de formación, y que pueda transferir lo que aprende a diferentes contextos y situaciones.</p>
  
  <p>Existen diferentes tipos de competencias de aprendizaje, según el ámbito o el nivel en que se apliquen. Para aplicar al sistema tutor inteligente se aplicaron tres competencias de aprendizajes como son: creatividad, resolución de problemas y pensamiento crítico.</p>
  
  <h4>1.1. Creatividad</h4>
  <img src="${require('@/assets/mecanica1.png')}
  " />   <div class="image-caption">
  Imagen 7: Descripción de las actividades basadas en la creatividad          </div>
  <p>Las actividades que potencian la creatividad están diseñadas según lo establecido por Edward de Bono, experto en creatividad y pensamiento lateral. Ha propuesto una serie de etapas para el desarrollo de la creatividad, ver <strong>Imagen 7</strong>. A continuación, se describen estas etapas:</p>
  
  <ul>
    <li><strong>Preparación:</strong> Esta etapa implica reunir toda la información y los conocimientos relevantes relacionados con el problema o la situación en la que se busca ser creativo. La preparación también puede incluir la identificación de patrones y tendencias que pueden ser útiles para resolver el problema.</li>
    <li><strong>Concentración:</strong> En esta etapa, se debe enfocar la atención en el problema o la situación y en los patrones y tendencias identificados durante la preparación. La concentración también implica evitar la distracción y mantener la mente enfocada en el objetivo creativo.</li>
    <li><strong>Generación de ideas:</strong> En esta etapa, se debe generar una amplia variedad de ideas y soluciones posibles, incluso aquellas que puedan parecer poco prácticas o convencionales. De Bono sugiere la utilización de técnicas de pensamiento lateral para fomentar la generación de ideas novedosas y creativas.</li>
    <li><strong>Desarrollo:</strong> Una vez que se han generado una serie de ideas, es importante desarrollarlas y explorar su viabilidad y relevancia para el problema o situación en cuestión. En esta etapa, se pueden combinar diferentes ideas y soluciones para crear nuevas y más efectivas.</li>
    <li><strong>Acción:</strong> La última etapa implica la implementación de la solución seleccionada y la evaluación de su efectividad. En esta etapa, es importante tomar medidas concretas para implementar la solución y hacer ajustes si es necesario.</li>
  </ul>
  
  <p>Además, el estudiante tiene la oportunidad de acceder a ejercicios, instrucciones y ayudas que complementan y sirven de apoyo y referente en el desarrollo de la actividad.</p>
  
  <h4>1.2. Resolución de problemas</h4>
  
   <img src="${require('@/assets/mecanica2.png')}
  " />   <div class="image-caption">
  Imagen 8: Descripción de las actividades de resolución de problemas.          </div>
  
  <p>Las actividades que potencian la resolución de problemas están diseñadas según lo establecido por George Polya, quien propuso un método para la resolución de problemas que consta de cuatro etapas, ver <strong>Imagen 8</strong>. A continuación, describiré cada una de estas etapas:</p>
  
  <ul>
    <li><strong>Comprender el problema:</strong> En esta etapa, es importante leer cuidadosamente el enunciado del problema y entender cuál es el objetivo que se busca alcanzar. También se deben identificar los datos relevantes y las restricciones que limitan la solución del problema.</li>
    <li><strong>Idear un plan:</strong> Una vez que se ha comprendido el problema, es importante idear un plan para encontrar una solución. Esto puede incluir la identificación de estrategias, técnicas o métodos que se pueden aplicar para resolver el problema.</li>
    <li><strong>Llevar a cabo el plan:</strong> En esta etapa, se debe aplicar el plan ideado para encontrar una solución al problema. Es importante ser metódico y cuidadoso al realizar los cálculos o procedimientos necesarios para resolver el problema.</li>
    <li><strong>Verificar la solución:</strong> La última etapa implica verificar que la solución encontrada es correcta y cumple con los requisitos del problema. Es importante revisar los cálculos y asegurarse de que no haya errores. También se puede comprobar la solución utilizando diferentes métodos o enfoques.</li>
  </ul>
  
  <h4>1.3. Pensamiento crítico</h4>
  
  <img src="${require('@/assets/mecanica3.png')}
  " />
    <div class="image-caption">
  Imagen 9: Descripción de las actividades de pensamiento crítico          </div>
  <p>Las actividades que potencian el pensamiento crítico están diseñadas según lo establecido por Richard Paul y Linda Elder, quienes diseñaron un modelo de pensamiento crítico que consta de seis etapas, ver <strong>Imagen 9</strong>. A continuación, describiré estas etapas:</p>
  
  <ul>
    <li><strong>Clarificar el problema:</strong> En esta etapa, se debe identificar y definir claramente el problema o la situación que se está analizando. Es importante comprender los hechos relevantes y las diferentes perspectivas que pueden existir.</li>
    <li><strong>Recopilar información:</strong> Una vez que se ha identificado el problema, es importante recopilar información relevante que pueda ayudar a comprenderlo mejor. Esto puede incluir la revisión de fuentes confiables, la consulta con expertos o la realización de observaciones directas.</li>
    <li><strong>Evaluar la información:</strong> En esta etapa, se debe evaluar críticamente la información recopilada y analizar su relevancia y fiabilidad. Es importante tener en cuenta los prejuicios y las suposiciones que pueden influir en la interpretación de la información.</li>
    <li><strong>Identificar suposiciones:</strong> En esta etapa, se deben identificar las suposiciones subyacentes que pueden estar influyendo en el análisis del problema. Es importante cuestionar estas suposiciones y considerar perspectivas alternativas.</li>
    <li><strong>Evaluar argumentos:</strong> En esta etapa, se deben evaluar críticamente los argumentos que se están utilizando para apoyar diferentes perspectivas o soluciones al problema. Esto implica analizar la lógica, la evidencia y la coherencia de los argumentos presentados.</li>
  </ul>
  <br>
  <p>Una vez explicado qué significa una mecánica de juego, se empieza a explicar cómo crear la mecánica de juego en la aplicación SGames21. La <strong>Imagen 10</strong> muestra el panel de administración del docente. Al dar clic en la primera opción subrayada, muestra el listado de las mecánicas creadas previamente. Para crear una mecánica de juego nueva, se debe dar clic en la segunda opción.</p>
  
  <p><img src="${require('@/assets/mecanica4.jpg')}" alt="Opción de crear una mecánica de juego" />  <div class="image-caption">
  Imagen 10: Opción de crear una mecánica de juego.          </div></p>
  
  <p>La <strong>Imagen 11</strong> muestra la vista para crear una mecánica de juego nueva. Para agregar el título a la mecánica de juego, se debe dar doble clic en el botón azul y agregar el título deseado.</p>
  
  <p><img src="${require('@/assets/mecanica5.jpg')}" alt="Vista para crear mecánica" />  <div class="image-caption">
  Imagen 11: Vista para crear mecánica.          </div></p>
  
  <p>Para agregar las fases de la mecánica de juego, se debe dar doble clic en el botón de color anaranjado, suprimir el texto de indicación y agregar el texto que corresponde al nombre de la fase de la mecánica de juego, como aparece en la <strong>Imagen 12</strong>.</p>
  
  <p><img src="${require('@/assets/mecanica6.jpg')}" alt="Agregar fase a la mecánica de juego" />  <div class="image-caption">
  Imagen 12: Agregar fase a la mecánica de juego.          </div></p>
  
  <p>La <strong>Imagen 13</strong> muestra la vista para agregar una nueva fase a la mecánica de juego. Se debe dar clic derecho sobre el título y seleccionar la opción que aparece en pantalla “Agregar fase”, de esa manera se pueden agregar las fases que sean necesarias.</p>
  
  <p><img src="${require('@/assets/mecanica7.jpg')}" alt="Agregar nueva fase" />
      <div class="image-caption">
  Imagen 13: Agregar nueva fase.          </div></p>
  
  <p>La <strong>Imagen 14</strong> muestra la opción de poder agregar una descripción a la mecánica de juego en el espacio subrayado de rojo.</p>
  
  <p><img src="${require('@/assets/mecanica8.jpg')}" alt="Agregar descripción a la mecánica de juego" />
     <div class="image-caption">
  Imagen 14: Agregar descripción a la mecánica de juego.   </div></p>
  
  <p>Una vez terminado el proceso de la creación de la mecánica de juego, se debe dar clic en el botón “GUARDAR” como aparece en la <strong>Imagen 15</strong>.</p>
  
  <p><img src="${require('@/assets/mecanicafaltante.jpg')}" alt="Guardar mecánica de juego" />
     <div class="image-caption">
  Imagen 15: Guardar mecánica de juego.    </div></p>
  
  <p>Una vez que se guarda la mecánica de juego, aparece en el listado de las mecánicas de juego creadas en el panel de administración del usuario docente, como se muestra en la <strong>Imagen 16</strong>.</p>
  
  <p><img src="${require('@/assets/mecanica9.jpg')}" alt="Mecánica de juego creada" />
     <div class="image-caption">
  Imagen 16: Mecánica de juego creada.      </div></p>` },
  
          { id: 'crearHistorias', title: 'Crear historias', content: ` <br><p>Antes de empezar a explicar el proceso para crear una historia, es importante que entienda el significado de una historia. Una historia está compuesta por tres niveles de complejidad según la taxonomía de Bloom (Ver <strong>Imagen 17</strong>). Esta taxonomía establece seis niveles de pensamiento cognitivo (Dimensión del proceso cognitivo), organizados en orden ascendente de complejidad: recordar, comprender, aplicar, analizar, evaluar y crear.</p>
  
  <p><img src="${require('@/assets/historias1.png')}" alt="Niveles de complejidad" />
     <div class="image-caption">
  Imagen 17: Niveles de complejidad.  
     </div></p>
  
  <p>Los niveles de la taxonomía de Bloom proponen estos seis niveles de pensamiento cognitivo, en orden ascendente, los cuales se describen a continuación:</p>
  
  <ul>
    <li><strong>Recordar:</strong> En este nivel, los estudiantes demuestran la capacidad de recuperar información previamente aprendida sin necesidad de entenderla o interpretarla en un contexto nuevo.</li>
    <li><strong>Comprender:</strong> En este nivel, los estudiantes demuestran la capacidad de entender la información y hacer inferencias a partir de ella. Además de recordarla, pueden explicarla y describirla en sus propias palabras.</li>
    <li><strong>Aplicar:</strong> En este nivel, los estudiantes pueden utilizar la información y los conceptos aprendidos en situaciones y contextos nuevos o diferentes. Pueden utilizar el conocimiento adquirido para resolver problemas o realizar tareas específicas.</li>
    <li><strong>Analizar:</strong> En este nivel, los estudiantes demuestran la capacidad de descomponer la información en partes más pequeñas y comprender las relaciones entre esas partes. Pueden identificar patrones, organizar la información de manera significativa y realizar inferencias basadas en el análisis.</li>
    <li><strong>Evaluar:</strong> En este nivel, los estudiantes pueden realizar juicios basados en criterios establecidos y estándares. Pueden evaluar la calidad, la efectividad o la validez de la información, los argumentos o los métodos utilizados.</li>
    <li><strong>Crear:</strong> En este nivel, los estudiantes demuestran la capacidad de combinar elementos de información y conocimiento para formar nuevos conceptos, ideas o productos. Pueden generar nuevas hipótesis, diseñar soluciones originales o crear obras basadas en su comprensión y aplicación del conocimiento.</li>
  </ul>
  
  <p>La taxonomía de Bloom también incluye la dimensión del conocimiento, que se refiere al tipo de conocimiento que se está evaluando en cada nivel. Esta dimensión abarca cuatro categorías: factual (hechos), conceptual (conceptos), procedural (procedimientos) y metacognitive (metacognitivo).</p>
  
  <p>La dimensión del conocimiento se refiere a los tipos de información que el estudiante debe manejar, como hechos, conceptos, procedimientos o metacognición. La dimensión del proceso cognitivo se refiere a las habilidades mentales que el estudiante debe desarrollar, como recordar, comprender, aplicar, analizar, evaluar o crear.</p>
  
  <p>Según el modelo que se muestra en la <strong>Imagen 18</strong>, la dimensión del conocimiento y el proceso cognitivo se combinan para formar una matriz de objetivos de aprendizaje, donde cada celda representa una categoría específica que orienta la enseñanza y la evaluación. Por ejemplo, un objetivo de aprendizaje podría ser que el estudiante recuerde los hechos sobre un tema, o que el estudiante cree un nuevo procedimiento para resolver un problema.</p>
  
  <p>En resumen, la adaptación de la taxonomía de Bloom proporciona una estructura actualizada y más completa para clasificar los niveles de pensamiento cognitivo, teniendo en cuenta la comprensión, aplicación y creación de conocimientos en contextos educativos y prácticos.</p>
  
  <p><img src="${require('@/assets/historias2.png')}" alt="Modelo según la taxonomía de Bloom" />
       <div class="image-caption">
  Imagen 18: Modelo según la taxonomía de Bloom.   </div></p></p>` },
  
          { id: 'datosIniciales', title: 'Datos iniciales de la historia', content: `<br><p>En esta sección se explicará el proceso que tiene que llevar a cabo el docente para poder crear una historia y así esta pueda estar disponible para el aprendizaje del estudiante.</p>
  
  
  <p>La <strong>Imagen 19</strong> muestra el panel de administración. Al dar clic en el botón número uno le aparece en pantalla la vista para empezar a crear la historia.</p>
  
  <p><img src="${require('@/assets/imagen19.jpg')}" alt="Personalización de la historia" />
       <div class="image-caption">
  Imagen 19: Panel de administración.   </div></p></p>
  
  <p>La <strong>Imagen 20</strong> muestra la vista de la creación de una historia. Lo primero que se debe hacer es agregar el título, un contexto, una descripción. Luego, se debe escoger un color o agregar una imagen de fondo para personalizar la historia.</p>
  
  <p><img src="${require('@/assets/imagen20.jpg')}" alt="Color de la historia" />
       <div class="image-caption">
  Imagen 20: Personalización de la historia.   </div></p></p>
  
  <p>Si se quiere escoger el color de la historia, se da clic en "color" y aparece un color sugerido. Si se da clic en el color sugerido, aparecerá la gama de colores disponibles para que se pueda escoger de todos los que aparecen en la <strong>Imagen 21</strong>.</p>
  
  <p><img src="${require('@/assets/imagen21.jpg')}" alt="Color de la historia" />
       <div class="image-caption">
  Imagen 21: Color de la historia.   </div></p></p>
  
  <p>Pero si lo que se quiere es agregar una imagen de fondo, se selecciona la opción "imagen" como aparece en la <strong>Imagen 22</strong>.</p>
  
  <p><img src="${require('@/assets/imagen22.jpg')}" alt="Imagen de fondo" />
       <div class="image-caption">
  Imagen 22: Imagen de fondo.   </div></p></p>
  
  <p>La <strong>Imagen 23</strong> muestra la vista para cargar la imagen de fondo de la historia. Se debe dar clic en el texto subrayado “O haz clic aquí”. Tenga en cuenta que la imagen debe pesar máximo 50 MB; si supera este peso, la aplicación le informará que supera el peso establecido de la imagen a cargar.</p>
  
  <p><img src="${require('@/assets/imagen23.jpg')}" alt="Cargar imagen de fondo" />
       <div class="image-caption">
  Imagen 23: Cargar imagen de fondo.   </div></p></p>
  
  <p>Una vez cargada la imagen de fondo, aparecerá en miniatura con el nombre y el formato de la imagen. Si se equivoca al momento de cargar la imagen, puede eliminarla dando clic en el botón de color rojo “Eliminar” que se muestra en la <strong>Imagen 24</strong>.</p>
  
  <p><img src="${require('@/assets/imagen24.jpg')}" alt="Imagen cargada" />
       <div class="image-caption">
  Imagen 24: Imagen cargada.   </div></p></p>
  
  <p>Luego, en la parte de abajo aparece la sección para cargar el logo de la historia. Debe dar clic en el texto subrayado “O haz clic aquí”, como se muestra en la <strong>Imagen 25</strong>. El logo le permite identificar visualmente la historia que se está creando.</p>
  
  <p><img src="${require('@/assets/imagen25.jpg')}" alt="Cargar logotipo de la historia" />
       <div class="image-caption">
  Imagen 25: Cargar logotipo de la historia.   </div></p></p>
  
  <p>Una vez se carga el logo a la sección, aparecerá en una imagen pequeña con el nombre y el formato. Si se equivoca al momento de subir la imagen, puede eliminarla dando clic en el botón rojo “Eliminar” como aparece en la <strong>Imagen 26</strong>.</p>
  
  <p><img src="${require('@/assets/imagen26.jpg')}" alt="Logo cargado" />
       <div class="image-caption">
  Imagen 26: Logo cargado.   </div></p></p>` },
  
          { id: 'retos', title: 'Retos de la historia', content: `<p>En esta sección se adicionarán los retos a la historia para continuar con el proceso de la creación de la historia completa.</p>
  
  <p>Por defecto aparece el primer reto. Si se desea agregar un reto, se debe dar clic en el botón en la parte de arriba llamado “ADICIONAR RETO” como aparece en la <strong>Imagen 27</strong>. Para empezar a agregar la información al reto 1, se debe dar clic en la lista desplegable.</p>
  
  <p><img src="${require('@/assets/imagen27.jpg')}" alt="Reto" />
       <div class="image-caption">
  Imagen 27: Reto.   </div></p></p>
  
  <p>La <strong>Imagen 28</strong> muestra el formulario para agregar toda la información al reto. Lo primero que se debe hacer es seleccionar la competencia de aprendizaje.</p>
  
  <p><img src="${require('@/assets/imagen28.jpg')}" alt="Formulario del reto" />
       <div class="image-caption">
  Imagen 28: Formulario del reto.   </div></p></p>
  
  <p>Al seleccionar la competencia, se desplegará una lista, en la cual aparecen todas las competencias de aprendizaje creadas previamente, como aparece en la <strong>Imagen 29</strong>. Escoja la competencia de aprendizaje que corresponda.</p>
  
  <p><img src="${require('@/assets/imagen29.jpg')}" alt="Lista desplegable de la competencia de aprendizaje" />
       <div class="image-caption">
  Imagen 29: Lista desplegable de la competencia de aprendizaje.
     </div></p></p>
  
  <p>Luego se debe escoger el nivel de dificultad del reto. Solo debe dar clic en “Seleccione la dificultad” y se desplegará una lista donde debe escoger si el reto lo prefiere fácil, medio o difícil, como se muestra en la <strong>Imagen 30</strong>.</p>
  
  <p><img src="${require('@/assets/imagen30.jpg')}" alt="Nivel de dificultad del reto" />
       <div class="image-caption">
  Imagen 30: Nivel de dificultad del reto.   </div></p></p>
  
  <p>Como tercer paso, se debe agregar una introducción al reto, como se muestra en la <strong>Imagen 31</strong>. Esta introducción permite familiarizar y contextualizar al estudiante al cual va dirigida la historia con el reto.</p>
  
  <p><img src="${require('@/assets/imagen31.jpg')}" alt="Introducción al reto" />
       <div class="image-caption">
  Imagen 31: Introducción al resto.   </div></p></p>
  
  <p>Como cuarto paso, tenemos dos tipos de fondos: el primero es añadir color o una imagen de fondo. Como se muestra en la <strong>Imagen 32</strong>.</p>
  
  <p><img src="${require('@/assets/imagen32.jpg')}" alt="Tipo de fondo" />
       <div class="image-caption">
  Imagen 32: Tipo de fondo.   </div></p></p>
  
  <p>Si se escoge el color como fondo del reto, aparecerán en pantalla los colores primarios más utilizados y la posibilidad de escoger más colores. Adicionalmente, se puede seleccionar el color por el código, como se muestra en la <strong>Imagen 33</strong>.</p>
  
  <p><img src="${require('@/assets/imagen33.jpg')}" alt="Color de fondo del reto" />
       <div class="image-caption">
  Imagen 33: Color de fondo del reto.   </div></p></p>
  
  <p>Pero si se escoge “Imagen” para el fondo del reto, aparecerá la sección que se muestra en la <strong>Imagen 34</strong>, y dar clic en el texto subrayado “O haz clic aquí” permite cargar la imagen que se desea colocar de fondo.</p>
  
  <p><img src="${require('@/assets/imagen34.jpg')}" alt="Imagen de fondo del reto" />
       <div class="image-caption">
  Imagen 34: Imagen de fondo del reto.   </div></p></p>
  
  <p>Una vez cargada la imagen de fondo, aparecerá en miniatura con el nombre y el formato de la imagen. Si se equivoca al momento de cargar la imagen, puede eliminarla dando clic en el botón de color rojo “Eliminar” que se muestra en la <strong>Imagen 35</strong>.</p>
  
  <p><img src="${require('@/assets/imagen35.jpg')}" alt="Imagen de fondo cargada" />
       <div class="image-caption">
  Imagen 35: Imagen de fondo cargada.
     </div>
     </p></p>`},
          { id: 'fases', title: 'Fases del reto', content: `
  <p>En esta sección se explica el proceso para agregar la información de las fases que corresponden al reto. El número de fases que se muestran depende de la competencia de aprendizaje escogida anteriormente. Se escoge la primera fase de ejemplo para demostrar cómo se carga la información.</p>
  
  <p><img src="${require('@/assets/imagen36.jpg')}" alt="Fases del reto" />
         <div class="image-caption">
  Imagen 36: Fases del reto.   </div></p>
  
  <p>Al dar clic en la primera fase, se despliega la primera actividad con el formulario que se ve en la <strong>Imagen 37</strong>. Lo recomendable es llenar el formulario secuencialmente.</p>
  
  <p><img src="${require('@/assets/imagen37.jpg')}" alt="Formulario de la primera actividad" />
         <div class="image-caption">
  Imagen 37: Formulario de la primera actividad.   </div></p>
  
  <p>Lo primero que se debe hacer es escribir el nombre de la primera actividad. Lo segundo es escoger la dimensión del proceso cognitivo. Al dar clic en “escoger la dimensión del proceso cognitivo” se despliega una lista con los que corresponden a la competencia que se escogió previamente. Escoja el que desee agregar, como se muestra en la <strong>Imagen 38</strong>.</p>
  
  <p><img src="${require('@/assets/imagen38.jpg')}" alt="Primera parte, información de la actividad" />
         <div class="image-caption">
  Imagen 38: Primera parte, información de la actividad.   </div></p>
  
  <p>Para seguir cargando la información de la actividad 1, se debe escribir el título, la introducción y la descripción de la actividad. Luego, se debe escoger entre dos opciones de fondo para la actividad: la primera es color y la segunda es imagen. La opción que escoja depende de la personalización que desea darle a la actividad, como se muestra en la <strong>Imagen 39</strong>.</p>
  
  <p><img src="${require('@/assets/imagen39.jpg')}" alt="Terminar de cargar la información a la primera actividad" />
         <div class="image-caption">
  Imagen 39: Terminar de cargar la información a la primera actividad.   </div></p>
  
  <p>La <strong>Imagen 40</strong> muestra una flecha apuntando al ícono “+”. Este ícono permite agregar una nueva actividad a la fase que se está editando. Solo debe dar clic en el ícono e inmediatamente saldrá el formulario de la nueva actividad.</p>
  
  <p><img src="${require('@/assets/imagen40.jpg')}" alt="Agregar nueva actividad" />
         <div class="image-caption">
  Imagen 40: Agregar nueva actividad.   </div></p>
  
  <p>Después de adicionar la información a la actividad, el siguiente paso es adicionar los minijuegos a la actividad. Tenga en cuenta que en la plataforma están disponibles distintos tipos de minijuegos, como son: arrastrar y soltar, collage, crossword, drag and words, fill blanks, secuencia de imagen y Cornell.</p>
  
  <p>Antes de escoger el tipo de minijuego, se debe escoger la dimensión del conocimiento que corresponde al minijuego que se va a añadir, especificar el valor de la recompensa y finalmente escoger el tipo de minijuego que se va a adicionar a la actividad, como se muestra en la <strong>Imagen 41</strong>.</p>
  
  <p><img src="${require('@/assets/imagen41.jpg')}" alt="Primer minijuego de la actividad" />
         <div class="image-caption">
  Imagen 41: Primer minijuego de la actividad.   </div></p>
  
  <p>Para escoger la dimensión del conocimiento, se da clic arriba de este nombre y aparece una lista desplegable. Del listado, escoja la dimensión del conocimiento que desea añadir, como se muestra en la <strong>Imagen 42</strong>.</p>
  
  <p><img src="${require('@/assets/imagen42.jpg')}" alt="Escoger la dimensión del conocimiento" />
         <div class="image-caption">
  Imagen 42: Escoger la dimensión del conocimiento.   </div></p>
  
  <p>Luego, se debe especificar el valor de la recompensa que corresponde al minijuego que se está configurando, como se muestra en la <strong>Imagen 43</strong>.</p>
  
  <p><img src="${require('@/assets/imagen43.jpg')}" alt="Recompensa del minijuego" />
         <div class="image-caption">
  Imagen 43: Recompensa del minijuego.   </div></p>
  
  <p>La <strong>Imagen 44</strong> muestra el listado de los tipos de minijuegos disponibles para configurar en la plataforma. Escoja el que prefiera añadir a la actividad.</p>
  
  <p><img src="${require('@/assets/imagen44.jpg')}" alt="Tipo de minijuego" />
         <div class="image-caption">
  Imagen 44: Tipo de minijuego.   </div></p>
  
  <h4>Minijuego de tipo Cornell</h4>
  
  <p>La <strong>Imagen 45</strong> muestra la opción subrayada en rojo, el botón “Adicionar pregunta”. Al dar clic sobre él, aparece el formulario para cargar las preguntas que tendrá el minijuego de tipo Cornell.</p>
  
  <p><img src="${require('@/assets/imagen45.jpg')}" alt="Adicionar pregunta al tipo de minijuego Cornell" />
         <div class="image-caption">
  Imagen 45: Adicionar pregunta al tipo de minijuego Cornell.   </div></p>
  
  <p>Las opciones que aparecen en el formulario que se muestra en la <strong>Imagen 46</strong> son: el enunciado de la pregunta, las opciones disponibles para la pregunta. Luego aparece el botón de “Adicionar opción” que al dar clic permite agregar una nueva opción a la pregunta. Por último, está el botón de “Eliminar pregunta”, al dar clic sobre él desaparece la pregunta inmediatamente.</p>
  
  <p><img src="${require('@/assets/imagen46.jpg')}" alt="Crear preguntas al minijuego" />
         <div class="image-caption">
  Imagen 46: Crear preguntas al minijuego.   </div></p>
  
  <h4>Minijuego de tipo arrastrar palabras</h4>
  
  <p>La <strong>Imagen 47</strong> muestra en el círculo rojo el ícono en forma de “+” que al dar clic sobre él permite agregar un nuevo minijuego a la actividad. Puede agregar los que considere pertinentes.</p>
  
  <p><img src="${require('@/assets/imagen47.jpg')}" alt="Agregar nuevo minijuego" />
         <div class="image-caption">
  Imagen 47: Agregar nuevo minijuego.   </div></p>
  
  <p>Una vez que ha agregado un nuevo minijuego, debe llenar el formulario del nuevo minijuego como se muestra en la <strong>Imagen 48</strong>. En este nuevo minijuego se escoge el tipo de minijuego arrastrar palabras.</p>
  
  <p><img src="${require('@/assets/imagen48.jpg')}" alt="Nuevo minijuego" />
         <div class="image-caption">
  Imagen 48: Nuevo minijuego.   </div></p>
  
  <p>Para este tipo de minijuego, se debe escribir un título y en el recuadro de abajo aparece la sección para cargar la imagen de fondo del minijuego. Solo debe dar clic en las palabras subrayadas “O haz clic aquí”, como se muestra en la <strong>Imagen 49</strong>.</p>
  
  <p><img src="${require('@/assets/imagen49.jpg')}" alt="Agregar título e imagen del nuevo minijuego" />
         <div class="image-caption">
  Imagen 49: Agregar título e imagen del nuevo minijuego.   </div></p>
  
  <p>La <strong>Imagen 50</strong> muestra los módulos de las imágenes que serán utilizadas para ser arrastradas. Se debe escribir el nombre y dar clic en las palabras subrayadas en rojo “O haz clic aquí”. De esta manera aparece la imagen cargada con su respectivo nombre.</p>
  
  <p><img src="${require('@/assets/imagen50.jpg')}" alt="Módulo de cargar imágenes para ser arrastradas" />
         <div class="image-caption">
  Imagen 50: Módulo de cargar imágenes para ser arrastradas.   </div></p>
  
  <p>Si desea agregar un nuevo módulo de imágenes para ser arrastradas, debe dar clic en el botón “Agregar nuevo” que se muestra subrayado en la <strong>Imagen 51</strong>.</p>
  
  <p><img src="${require('@/assets/imagen51.jpg')}" alt="Agregar nuevo módulo" />
         <div class="image-caption">
  Imagen 51: Agregar nuevo módulo.   </div></p>
  
  <p>La <strong>Imagen 52</strong> muestra el nuevo minijuego que se adiciona a la actividad. Este juego se llama arrastrar palabra y permite arrastrar las palabras a la imagen que corresponde.</p>
  
  <p><img src="${require('@/assets/imagen52.jpg')}" alt="Minijuego arrastrar palabras" />
         <div class="image-caption">
  Imagen 52: Minijuego arrastrar palabras.   </div></p>
  
  <p>Cuando se escoge el minijuego de arrastrar palabra, aparece la vista que muestra la <strong>Imagen 53</strong>. En esta se debe agregar el título del minijuego y luego agregar una imagen de fondo, como se muestra subrayado en color rojo.</p>
  
  <p><img src="${require('@/assets/imagen53.jpg')}" alt="Título e imagen de fondo del minijuego" />
         <div class="image-caption">
  Imagen 53: Título e imagen de fondo del minijuego.   </div></p>
  
  <p>Cuando se ha terminado de cargar la información en el formulario del minijuego arrastra las palabras, se ve como se muestra en la <strong>Imagen 54</strong>. Luego, en la parte de abajo, el botón que se muestra subrayado en rojo debe ser clickeado para cargar las palabras y las imágenes que van a ser arrastradas.</p>
  
  <p><img src="${require('@/assets/imagen54.jpg')}" alt="Información cargada del minijuego" />
         <div class="image-caption">
  Imagen 54: Información cargada del minijuego.   </div></p>
  
  <p>La <strong>Imagen 55</strong> muestra los módulos donde se debe agregar la palabra y el espacio de cargar la imagen que corresponde a esta. Si desea agregar otro módulo, puede hacerlo dando clic en el botón subrayado en rojo llamado “Agregar nuevo”.</p>
  
  <p><img src="${require('@/assets/imagen55.jpg')}" alt="Agregar nuevo módulo" />
         <div class="image-caption">
  Imagen 55: Agregar nuevo módulo.   </div></p>
  
  <p>Si ya ha terminado de cargar toda la información al minijuego, debe dar clic en el botón subrayado “Actualizar” para poder guardar dicha información, como se muestra en la <strong>Imagen 56</strong>.</p>
  
  <p><img src="${require('@/assets/imagen56.jpg')}" alt="Guardar información del minijuego" />
         <div class="image-caption">
  Imagen 56: Guardar información del minijuego.   </div></p>
  
  <h4>Minijuego de tipo quiz ordenado</h4>
  
  <p>A continuación, se muestra la <strong>Imagen 57</strong> donde se muestra un formulario y un texto subrayado en rojo. Este es el minijuego nuevo que se va a crear de tipo “Quiz ordenado”, el cual permite ordenar un texto de acuerdo con el enunciado.</p>
  
  <p><img src="${require('@/assets/imagen57.jpg')}" alt="Quiz ordenado" />
         <div class="image-caption">
  Imagen 57: Quiz ordenado.   </div></p>
  
  <p>La <strong>Imagen 58</strong> muestra el formulario donde se debe cargar la información del minijuego de tipo quiz ordenado. Se debe escoger la dimensión del conocimiento para este minijuego que se está creando, escribir la recompensa y el tipo de minijuego. El botón subrayado en rojo llamado “Adicionar pregunta” permite adicionar una pregunta y las respuestas que van a ser ordenadas.</p>
  
  <p><img src="${require('@/assets/imagen58.jpg')}" alt="Adicionar pregunta al minijuego de tipo quiz ordenado" />
         <div class="image-caption">
  Imagen 58: Adicionar pregunta al minijuego de tipo quiz ordenado.   </div></p>
  
  <p>Al momento de adicionar una pregunta, aparece el formulario que se debe editar. Lo primero que se debe hacer es agregar el enunciado a la pregunta, luego los campos a ordenar que corresponden al enunciado de esa pregunta. Si desea eliminar toda la pregunta, debe dar clic en “Eliminar pregunta”, como se muestra en la <strong>Imagen 59</strong>.</p>
  
  <p><img src="${require('@/assets/imagen59.jpg')}" alt="Formulario de la pregunta del minijuego de tipo quiz ordenado" />
         <div class="image-caption">
  Imagen 59: Formulario de la pregunta del minijuego de tipo quiz ordenado.   </div></p>
  
  <p>Si desea agregar un campo a la pregunta, puede hacerlo dando clic en el botón “Adicionar opción” que aparece subrayado en rojo en la <strong>Imagen 60</strong>.</p>
  
  <p><img src="${require('@/assets/imagen60.jpg')}" alt="Adicionar opción a la pregunta" />
         <div class="image-caption">
  Imagen 60: Adicionar opción a la pregunta.   </div></p>
  
  <p>Cuando se agrega una nueva opción, aparece un campo que se debe llenar con la información correspondiente a ese campo, como se muestra en la <strong>Imagen 61</strong>.</p>
  
  <p><img src="${require('@/assets/imagen61.jpg')}" alt="Nueva opción" />
         <div class="image-caption">
  Imagen 61: Nueva opción.   </div></p>
  
  <p>Si se desea agregar una nueva pregunta con información que se quiera ordenar, debe dar clic en el botón subrayado en color rojo, como se muestra en la <strong>Imagen 62</strong>.</p>
  
  <p><img src="${require('@/assets/imagen62.jpg')}" alt="Adicionar nueva pregunta al quiz ordenado" />
         <div class="image-caption">
  Imagen 62: Adicionar nueva pregunta al quiz ordenado.   </div></p>
  
  <p>Cuando se termina de cargar toda la información al minijuego de quiz ordenado, se debe dar clic en el botón “Actualizar” que se muestra subrayado de color rojo en la parte de debajo de la <strong>Imagen 63</strong>.</p>
  
  <p><img src="${require('@/assets/imagen63.jpg')}" alt="Guardar información del minijuego" />
         <div class="image-caption">
  Imagen 63: Guardar información del minijuego.   </div></p>
  
  <h4>Minijuego de tipo crucigrama</h4>
  
  <p>El nuevo minijuego que se va a agregar es de tipo crucigrama. En este, se permite llenar con letras las casillas de una cuadrícula de modo que formen en sentido horizontal y vertical ciertas palabras determinadas por definiciones dadas. Para que esto se dé, se deben llevar a cabo unos pasos previamente. En el listado que se lista, se debe escoger el minijuego de tipo crucigrama, como se muestra en la <strong>Imagen 64</strong>.</p>
  
  <p><img src="${require('@/assets/imagen64.jpg')}" alt="Minijuego de tipo crucigrama" />
         <div class="image-caption">
  Imagen 64: Minijuego de tipo crucigrama.   </div></p>
  
  <p>La <strong>Imagen 65</strong> muestra dos cuadrados. En el primero se debe escribir la palabra que va a contener el crucigrama y en el segundo cuadrado se escribe el texto de pista para poder escribir la palabra correcta, escrita previamente.</p>
  
  <p><img src="${require('@/assets/imagen65.jpg')}" alt="Módulo del minijuego crucigrama" />
         <div class="image-caption">
  Imagen 65: Módulo del minijuego crucigrama.   </div></p>
  
  <p>Para agregar una nueva palabra al crucigrama, se debe dar clic en el botón llamado “Agregar palabras”, como se muestra en la <strong>Imagen 66</strong>.</p>
  
  <p><img src="${require('@/assets/imagen66.jpg')}" alt="Agregar palabras al crucigrama" />
         <div class="image-caption">
  Imagen 66: Agregar palabras al crucigrama.   </div></p>
  
  <p>La <strong>Imagen 67</strong> muestra el nuevo módulo de la palabra que se va a agregar, que contiene la palabra y la pista de la palabra.</p>
  
  <p><img src="${require('@/assets/imagen67.jpg')}" alt="Nueva palabra al crucigrama" />
         <div class="image-caption">
  Imagen 67: Nueva palabra al crucigrama.   </div></p>
  
  <p>Una vez que se terminan de llenar las palabras y sus pistas, se genera el crucigrama con todas las palabras ordenadas horizontal y verticalmente. Para esto, se debe dar clic en el botón subrayado en rojo llamado “Generar crucigrama”, como se muestra en la <strong>Imagen 68</strong>.</p>
  
  <p><img src="${require('@/assets/imagen68.jpg')}" alt="Generar crucigrama" />
         <div class="image-caption">
  Imagen 68: Generar crucigrama.   </div></p>
  
  <p>La <strong>Imagen 69</strong> muestra el crucigrama generado a partir de las palabras establecidas previamente.</p>
  
  <p><img src="${require('@/assets/imagen69.jpg')}" alt="Crucigrama generado" />
         <div class="image-caption">
  Imagen 69: Crucigrama generado.   </div></p>
  
  <p>Una vez que se termina de cargar la información de la historia con los retos y las fases, se debe dar clic en el botón señalado por la flecha de color rojo para guardar la historia, como aparece en la <strong>Imagen 70</strong>.</p>
  
  <p><img src="${require('@/assets/imagen70.jpg')}" alt="Guardar minijuego" />
         <div class="image-caption">
  Imagen 70: Guardar minijuego.   </div></p>
  
  <p>Una vez que se guarda la información de la historia, aparece en la opción señalada en color rojo. Esta opción permite ver las historias creadas previamente, como se muestra en la <strong>Imagen 71</strong>.</p>
  
  <p><img src="${require('@/assets/imagen71.jpg')}" alt="Ver las historias creadas" />
         <div class="image-caption">
  Imagen 71: Ver las historias creadas.   </div></p>
  
  <p>La <strong>Imagen 72</strong> muestra el listado de las historias creadas. Aparece el nombre con el que se registró la historia. Adicionalmente, al frente aparecen dos opciones: la primera opción es en forma de lápiz, que permite editar la historia; y la segunda opción es en forma de canasta, que permite eliminar esa historia.</p>
  
  <p><img src="${require('@/assets/imagen72.jpg')}" alt="Listado historias creadas" />
         <div class="image-caption">
  Imagen 72: Listado historias creadas.   </div></p>
  
  <p>Al dar clic en el botón señalado que aparece en forma de canasta, como se muestra en la <strong>Imagen 73</strong>, se elimina la historia inmediatamente de manera permanente. Se le aconseja que esté seguro de que quiere eliminar la historia.</p>
  
  <p><img src="${require('@/assets/imagen73.jpg')}" alt="Opción eliminar historia" />
         <div class="image-caption">
  Imagen 73: Opción eliminar historia.   </div></p>` },
  
  {
    id: 'Crear curso',
    title: 'Crear curso',
    content: `<br>
      <p>A continuación, se explicará el proceso para crear un curso dirigido a los estudiantes de secundaria del departamento de Córdoba. En el panel de administración se permite crear un nuevo curso o actualizar los que están realizados; solo debe dar clic en el cuadro como se muestra en la <strong>Imagen 74</strong>.</p>
  
  <p><img src="${require('@/assets/imagen74.jpg')}" alt="Crear o actualizar el curso" />
         <div class="image-caption">
  Imagen 74: Crear o actualizar el curso.   </div></p>
  
  <p>Para empezar a crear el curso desde cero, con las historias correspondientes, debe dar clic en la opción señalada en rojo, como se muestra subrayada en la <strong>Imagen 75</strong>.</p>
  
  <p><img src="${require('@/assets/imagen75.jpg')}" alt="Crear nuevo curso" />
         <div class="image-caption">
  Imagen 75: Crear nuevo curso.   </div></p>
  
  <p>Cuando se empieza a crear el curso, lo primero que se debe hacer es escoger el tema. Este permite saber de qué va a tratar el curso. Como se muestra en la <strong>Imagen 76</strong>.</p>
  
  <p><img src="${require('@/assets/imagen76.jpg')}" alt="Escoge el tema del curso" />
         <div class="image-caption">
  Imagen 76: Escoge el tema del curso   </div></p>
  
  <p>Una vez escogido el tema, se debe escribir el título, una descripción y una introducción del curso, esto con el fin de colocar en contexto al estudiante sobre el curso, como se muestra en la <strong>Imagen 77</strong>.</p>
  
  <p><img src="${require('@/assets/imagen77.jpg')}" alt="Título, descripción e introducción del curso" />
         <div class="image-caption">
  Imagen 77: Título, descripción e introducción del curso.   </div></p>
  
  <p>Luego, lo que hacemos es escoger el tipo de fondo. Existen dos opciones, las cuales son: color de la imagen. Usted decide cuál quiere escoger. En este ejemplo se escoge el color de fondo, como se muestra en la <strong>Imagen 78</strong>.</p>
  
  <p><img src="${require('@/assets/imagen78.jpg')}" alt="Escoger el fondo del curso" />
         <div class="image-caption">
  Imagen 78: Escoger el fondo del curso.   </div></p>
  
  <p>Una vez se escoge el color de fondo, aparece un cuadro con colores (ver <strong>Imagen 79</strong>), de los cuales usted elige el que mejor se ajuste al curso que está creando.</p>
  
  <p><img src="${require('@/assets/imagen79.jpg')}" alt="Color de fondo del curso" />
         <div class="image-caption">
  Imagen 79: Color de fondo del curso.   </div></p>
  
  <p>Lo siguiente que se debe hacer para continuar con el proceso de crear el curso es agregar el logo al curso. Debe adicionar el logo en formato imagen (.PNG, .JPEG, etc.), como se muestra subrayada en la <strong>Imagen 80</strong>.</p>
  
  <p><img src="${require('@/assets/imagen80.jpg')}" alt="Agregar el logo del curso" />
         <div class="image-caption">
  Imagen 80: Agregar el logo del curso.   </div></p>
  
  <p>Una vez se agrega la información al curso, como segundo punto se deben escoger las historias que se desean agregar al curso. En el recuadro subrayado en rojo, se debe adicionar una palabra clave que corresponda al nombre de la historia y se debe dar clic en el botón “Buscar”, para ver los resultados de esa búsqueda.</p>
  
  <p><img src="${require('@/assets/imagen81.jpg')}" alt="Buscar historias para agregar al curso" />
         <div class="image-caption">
  Imagen 81: Buscar historias para agregar al curso.   </div></p>
  
  <p>La <strong>Imagen 82</strong> muestra los resultados de la búsqueda hecha. Usted elige la historia que quiere agregar; si no corresponden los resultados con la búsqueda que hizo, intente con una nueva palabra y repita el proceso nuevamente.</p>
  
  <p><img src="${require('@/assets/imagen82.jpg')}" alt="Listado de las historias encontradas de acuerdo con la búsqueda" />
         <div class="image-caption">
  Imagen 82: Listado de las historias encontradas de acuerdo con la búsqueda.   </div></p>
  
  <p>La <strong>Imagen 83</strong> muestra la historia seleccionada para ser agregada al curso.</p>
  
  <p><img src="${require('@/assets/imagen83.jpg')}" alt="Seleccionar la historia" />
         <div class="image-caption">
  Imagen 83: Seleccionar la historia.   </div></p>
  
  <p>Cuando se termina de crear el curso, el curso que usted creó aparece en la sección señalada en rojo en la <strong>Imagen 84</strong>.</p>
  
  <p><img src="${require('@/assets/imagen84.jpg')}" alt="Listado de los cursos creados" />
         <div class="image-caption">
  Imagen 84: Listado de los cursos creados.   </div></p>
  
  <p>Al curso creado le aparecen dos opciones. La primera, que aparece subrayada en rojo en la <strong>Imagen 85</strong>, permite editar o hacer cambios al curso creado, en caso de que desee cambiar algo del curso.</p>
  
  <p><img src="${require('@/assets/imagen85.jpg')}" alt="Editar el curso creado previamente" />
         <div class="image-caption">
  Imagen 85: Editar el curso creado previamente.
     </div></p>
  
  <p>Una vez termine de editar el curso, lo siguiente que se hace es dar clic en “Actualizar”, como se muestra en la <strong>Imagen 86</strong>.</p>
  
  <p><img src="${require('@/assets/imagen86.jpg')}" alt="Actualizar el curso editado" />
         <div class="image-caption">
  Imagen 86: Actualizar el curso editado.   </div></p>
  
  <p>La segunda opción que aparece en los cursos creados es la opción de eliminar. Esta permite eliminar el curso que ha creado, como se muestra en la <strong>Imagen 87</strong>.</p>
  
  <p><img src="${require('@/assets/imagen87.jpg')}" alt="Eliminar el curso" />
         <div class="image-caption">
  Imagen 87: Eliminar el curso.   </div></p>
  
  <p>Al dar clic en la opción de eliminar el curso, verá que el curso que había creado no aparece en la lista de cursos creados, como se muestra en la <strong>Imagen 88</strong>.</p>
  
  <p><img src="${require('@/assets/imagen88.jpg')}" alt="Curso eliminado" />
         <div class="image-caption">
  Imagen 88: Curso eliminado.   </div></p>
    `
  }
        ]
      };
    },
    methods: {
      scrollToSection(id) {
        const element = document.getElementById(id);
        if (element) {
          element.scrollIntoView({ behavior: 'smooth' })
        }
        this.drawer = false
      }
    }
  };
  </script>
  
  
  
  <style>
  
  @font-face {
    font-family: 'Answer';
    src: url('assets/fonts/Game Played.otf') format('truetype')
         ;
    font-weight: normal;
    font-style: normal;
  }
  
  
  .section {
    padding: 40px;
  }
  
  .custom-drawer {
    background-color: #f5f5f5; /* Fondo gris claro */
    border-right: 2px solid #9c27b0; /* Línea morada a la derecha */
    padding: 10px
  }
  
  .logo-item {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .logo {
    max-width: 150px; /* Tamaño del logo */
    ;
  }
  
  .list-item {
    border-radius: 20px;
    
  }
  
  .list-item .v-list-item-title {
    color: #d900ff; /* Texto morado */
  }
  
  .titlenavi {
    color: #ffffff; /* Texto morado */
    font-family: 'answer', sans-serif;
    text-align: left;

  }
  
  
  
  .list-item:hover {
    background-color: #0d2769; /* Fondo morado claro al pasar el ratón */
  
  }
  
  .section-title {
    background-image: url('@/assets/game.svg');
    background-size: cover; /* Ajusta la imagen de fondo para cubrir todo el área */
    background-repeat: no-repeat; /* Evita que la imagen se repita */
    background-position: center; /* Centra la imagen de fondo */
    padding: 15px;
    text-align: center; /* Centrar el texto */
    width: 100%; /* Ocupa todo el ancho del contenedor */
    box-sizing: border-box; /* Incluye padding y border en el cálculo del ancho */
    min-height: 150px; /* Altura mínima fija */
  }
  
  .section-title h2 {
    margin: 0; /* Eliminar margen por defecto */
    font-size: 3rem; /* Tamaño de fuente grande */
    color: white;
    font-family: 'Answer', sans-serif;
  
  
  }
  
  .into {
   height: auto
  }
  
  .main {
   background-color: #e4e4e4;
   margin: 0;
   padding: 0;
  
  } 
  
  p {
  color: rgb(73, 73, 73);
  font-family: "Poppins", sans-serif;
  text-align: left;
  } 
  img {
  width: 100%;
  object-fit: cover;
  object-position: bottom;
  } 
  
  @media (max-width: 960px) {
  .v-navigation-drawer {
    position: fixed !important;
  }
}
  
  .image-caption {
    text-align: center;
    font-size: 14px;
    margin-top: 5px;
    font-family: 'Answer', sans-serif; /* Usa la fuente personalizada aquí */
    color: rgb(0, 155, 216);
    text-decoration: underline
  }
  
  
  
  
  
  @import url('https://fonts.googleapis.com/css2?family=Abril+Fatface&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
  </style>