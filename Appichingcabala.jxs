import React, { useState } from 'react';

// =======================
//   DATOS CABALÍSTICOS
// =======================

const CABALA_HEXAGRAMAS = {
  1: {
    sephirah: 'Kéter (Corona)',
    meaning: 'Voluntad esencial, origen del propósito.',
    innerWork:
      'Vuelve a la intención raíz de esta situación y deja que sea el eje de tus decisiones hoy.',
    ichingMeaning:
      'Lo Creativo. La fuerza primordial y el origen de todo. Se requiere perseverancia y claridad de intención para manifestar el propósito.',
  },
  2: {
    sephirah: 'Maljut (Reino)',
    meaning: 'Manifestación concreta: cuerpo, casa, dinero, territorio.',
    innerWork:
      'Ordena tu entorno y tus rutinas; pregúntate qué necesitas nutrir en silencio antes de empujar de nuevo.',
    ichingMeaning:
      'Lo Receptivo. La Tierra que acoge y sustenta. La acción debe ser secundaria a la dirección de otro; la humildad trae éxito duradero.',
  },
  3: {
    sephirah: 'Yesod (Fundación)',
    meaning: 'Caos fértil, gestación, puente entre lo invisible y lo visible.',
    innerWork:
      'Acepta la confusión actual, escribe lo que quieres y desglósalo en pasos pequeños y pedibles.',
    ichingMeaning:
      'El Brote. El momento de la dificultad inicial donde todo comienza. La clave es la paciencia; no te precipites, consolida la base.',
  },
  4: {
    sephirah: 'Hod (Gloria / Intelecto)',
    meaning: 'Aprendizaje, estructura mental, necesidad de método.',
    innerWork:
      'Elige un solo método o referencia y comprométete con él para ordenar tu mente y tu estudio.',
    ichingMeaning:
      'La Juventud Inexperta. Se necesita educación y guía. La receptividad para aprender es crucial, pero la insistencia necia no es bienvenida.',
  },
  5: {
    sephirah: 'Jesed (Misericordia / Expansión)',
    meaning: 'Confianza en el tiempo, lluvia que llega a su hora.',
    innerWork:
      'En lugar de forzar, cuida tus recursos y vínculos mientras esperas la señal clara para actuar.',
    ichingMeaning:
      'La Espera. El peligro está presente, pero el tiempo es favorable. Mantente firme y sereno, pues la providencia llegará.',
  },
  6: {
    sephirah: 'Guevurá (Rigor / Juicio)',
    meaning: 'Conflicto, cortes necesarios, límites claros.',
    innerWork:
      'Más que ganar una discusión, define el límite sano que necesitas afirmar sin culpa.',
    ichingMeaning:
      'El Conflicto. La discusión surge cuando los intereses chocan. Retirarse a tiempo o buscar una mediación superior es más sabio que insistir en la batalla.',
  },
  7: {
    sephirah: 'Guevurá',
    meaning: 'Disciplina organizada, energía bajo mando.',
    innerWork:
      'Ordena tus fuerzas: diseña una estrategia simple y sigue ese plan sin dispersarte en frentes secundarios.',
    ichingMeaning:
      'El Ejército. La disciplina y la organización son vitales. Se necesita un mando claro y un objetivo moral para lograr la cohesión.',
  },
  8: {
    sephirah: 'Jesed',
    meaning: 'Cohesión, pertenencia, unión afectiva.',
    innerWork:
      'Pregúntate con quién quieres realmente caminar y cómo puedes cuidar la confianza dentro de ese círculo.',
    ichingMeaning:
      'La Solidaridad. Unirse en un propósito común. La honestidad y el respeto mutuo son la base para una unión fuerte y exitosa.',
  },
  9: {
    sephirah: 'Hod',
    meaning: 'Pequeñas correcciones, ajustes de forma.',
    innerWork:
      'No busques un cambio gigante: elige un hábito minúsculo que puedas sostener cada día.',
    ichingMeaning:
      'El Poder de lo Pequeño. La fuerza de la influencia sutil. Retener la fuerza y nutrirla en la quietud; el éxito llega por la paciencia y la atención al detalle.',
  },
  10: {
    sephirah: 'Tiferet (Belleza / Corazón)',
    meaning: 'Dignidad, forma correcta de actuar.',
    innerWork:
      'Observa tu conducta cotidiana y ajústala para que refleje el valor y la verdad que llevas dentro.',
    ichingMeaning:
      'El Caminar. Comportarse con dignidad y cautela ante el peligro. Mantener la ligereza y la gracia a pesar de las circunstancias difíciles.',
  },
  11: {
    sephirah: 'Tiferet',
    meaning: 'Armonía cielo–tierra, equilibrio fértil.',
    innerWork:
      'Reconoce lo que ya está en paz y úsalo como base para ordenar lo pendiente sin dramatizar.',
    ichingMeaning:
      'La Paz. Armonía y prosperidad. El Cielo está sobre la Tierra. Momento de gozo, pero es crucial mantener la precaución y no caer en el exceso.',
  },
  12: {
    sephirah: 'Biná (Entendimiento)',
    meaning: 'Estancamiento estructural, límite que no se mueve.',
    innerWork:
      'Acepta qué no depende de ti cambiar ahora y decide dónde sí puedes actuar con realismo.',
    ichingMeaning:
      'El Estancamiento. Las fuerzas negativas prevalecen y el avance es imposible. Es tiempo de replegarse, cultivar lo interno y aceptar el límite externo.',
  },
  13: {
    sephirah: 'Jesed',
    meaning: 'Apertura al colectivo, fraternidad desde la esencia.',
    innerWork:
      'Muestra con honestidad quién eres y acércate a espacios donde esa autenticidad pueda sostenerse.',
    ichingMeaning:
      'La Convivencia. Unión de hombres. El corazón abierto y la visión clara crean comunidad. La clave está en la sinceridad y la amistad.',
  },
  14: {
    sephirah: 'Jesed',
    meaning: 'Abundancia responsable, expansión luminosa.',
    innerWork:
      'Reconoce tus dones reales y comparte una parte sin caer ni en la soberbia ni en la falsa humildad.',
    ichingMeaning:
      'La Posesión de lo Grande. Prosperidad y riqueza, material o espiritual. La magnanimidad y el uso ético de los recursos son esenciales.',
  },
  15: {
    sephirah: 'Maljut',
    meaning: 'Humildad, sencillez aplicada a lo concreto.',
    innerWork:
      'Reduce lo superfluo y deja que hablen tus actos pequeños y constantes en vez de tu autoimagen.',
    ichingMeaning:
      'La Modestia. Éxito duradero a través de la humildad y la sencillez. La grandeza interior no necesita exhibirse, sino aplicarse al bien común.',
  },
  16: {
    sephirah: 'Netzaj (Victoria / Deseo)',
    meaning: 'Entusiasmo, impulso motivador.',
    innerWork:
      'Canaliza tu entusiasmo hacia un proyecto concreto en vez de perderlo en fantasías dispersas.',
    ichingMeaning:
      'El Entusiasmo. Alegría y motivación que inspira a otros. Es un llamado a la acción, pero debe estar basado en una visión clara y una preparación seria.',
  },
  17: {
    sephirah: 'Netzaj',
    meaning: 'Seguir un ritmo, alinearse con una guía.',
    innerWork:
      'Revisa a quién o a qué estás siguiendo y si todavía resuena con tu verdad actual.',
    ichingMeaning:
      'El Seguimiento. Adaptarse a las circunstancias y fluir con el tiempo. Es necesario saber a quién o qué seguir y mantener la lealtad al propósito.',
  },
  18: {
    sephirah: 'Biná',
    meaning: 'Revisión del pasado, reparación paciente.',
    innerWork:
      'Nombra sin maquillaje lo que se corrompió y da un gesto práctico, pequeño y realista para repararlo.',
    ichingMeaning:
      'El Arreglo. Corrupción y deterioro. Esfuerzo paciente para rectificar errores pasados. La renovación debe ser profunda y responsable.',
  },
  19: {
    sephirah: 'Jesed',
    meaning: 'Acercamiento progresivo, apertura benevolente.',
    innerWork:
      'Da tú un paso claro y amable hacia lo que deseas sin exigir una respuesta inmediata.',
    ichingMeaning:
      'El Acercamiento. Momento de avance positivo y crecimiento. El éxito está garantizado si actúas con alegría, humildad y una visión de largo plazo.',
  },
  20: {
    sephirah: 'Tiferet',
    meaning: 'Contemplación, visión del conjunto.',
    innerWork:
      'Toma distancia, observa la escena como si fueras testigo y deja que la comprensión llegue antes de moverte.',
    ichingMeaning:
      'La Contemplación. Observar y examinar el mundo y a uno mismo. El líder debe ser un espejo claro para que los demás puedan verse y corregirse.',
  },
  21: {
    sephirah: 'Guevurá',
    meaning: 'Juicio, morder lo que obstruye.',
    innerWork:
      'Sé tajante con aquello que sabes que bloquea el camino, aunque implique incomodar o decir que no.',
    ichingMeaning:
      'La Mordedura. El obstáculo debe ser eliminado por la fuerza de la ley. Es necesaria una acción decidida y justa para hacer cumplir los límites.',
  },
  22: {
    sephirah: 'Netzaj',
    meaning: 'Belleza expresiva, gracia en la forma.',
    innerWork:
      'Cuida la forma en que dices y presentas las cosas; tu mensaje necesita un cuerpo bello y claro.',
    ichingMeaning:
      'La Gracia. El adorno y la belleza en la forma. La esencia debe ser adornada con gusto, pero el adorno no debe primar sobre el contenido.',
  },
  23: {
    sephirah: 'Biná',
    meaning: 'Desintegración, caída de lo viejo.',
    innerWork:
      'Reconoce qué estructura ya está muriendo y deja que caiga en lugar de sostener ruinas por costumbre.',
    ichingMeaning:
      'La Desintegración. Las fuerzas negativas erosionan lo sólido. Retirada necesaria, no resistas la caída; acepta la pérdida y espera el retorno.',
  },
  24: {
    sephirah: 'Yesod',
    meaning: 'Retorno cíclico, punto de giro interior.',
    innerWork:
      'Regresa a una práctica simple que ya sabes que te centra, aunque sea por pocos minutos al día.',
    ichingMeaning:
      'El Retorno. El inicio de un nuevo ciclo. Después de la desintegración, la luz regresa. La acción debe ser simple y directa, volviendo al punto de origen.',
  },
  25: {
    sephirah: 'Tiferet',
    meaning: 'Inocencia, corazón espontáneo.',
    innerWork:
      'Haz lo que sientes correcto aunque no tengas garantías de resultado ni de aprobación externa.',
    ichingMeaning:
      'La Inocencia. La verdad sin artificios. Actuar desde la espontaneidad y la pureza de corazón. El éxito llega si no se buscan ganancias externas.',
  },
  26: {
    sephirah: 'Guevurá',
    meaning: 'Contención de poder, freno consciente.',
    innerWork:
      'Cultiva tu fuerza en silencio: retén, pule y madura antes de dar un gran movimiento hacia fuera.',
    ichingMeaning:
      'La Fuerza Domada. La Gran Contención. Esfuerzo consciente por nutrir y acumular fuerza. La paciencia es la clave antes de emprender grandes obras.',
  },
  27: {
    sephirah: 'Yesod',
    meaning: 'Nutrición, boca, alimento físico y simbólico.',
    innerWork:
      'Observa qué estás comiendo, leyendo y escuchando, y elige alimentar lo que sostiene tu centro.',
    ichingMeaning:
      'El Sustento. La provisión de alimento para el cuerpo y el espíritu. Reflexionar sobre lo que se ingiere y sobre el modo de proveer para otros.',
  },
  28: {
    sephirah: 'Biná',
    meaning: 'Carga excesiva, peso sobre los hombros.',
    innerWork:
      'Distingue qué peso no te corresponde y suelta al menos una obligación que ya no es tuya.',
    ichingMeaning:
      'La Preponderancia de lo Grande. Peso excesivo que amenaza con la rotura. Se requiere una acción firme y audaz para resolver la sobrecarga, actuando sin miedo.',
  },
  29: {
    sephirah: 'Yesod',
    meaning: 'Abismo emocional, pruebas repetidas.',
    innerWork:
      'Reconoce el patrón que se repite y pregúntate qué verdad interna todavía evitas mirar de frente.',
    ichingMeaning:
      'El Abismo. Peligro repetido. La constancia y la profundidad interior son las únicas defensas. No te dejes atrapar por el miedo, busca la verdad en el centro.',
  },
  30: {
    sephirah: 'Jojmá (Sabiduría)',
    meaning: 'Luz adherente, claridad que ilumina.',
    innerWork:
      'Define la verdad que quieres sostener y diseña una forma diaria de mantener esa llama encendida.',
    ichingMeaning:
      'Lo Adherente. El Fuego, la luz que ilumina y se adhiere. Mantener la claridad mental y la conciencia en todo momento; la dependencia en la luz correcta trae éxito.',
  },
  31: {
    sephirah: 'Netzaj',
    meaning: 'Atracción, magnetismo, eros.',
    innerWork:
      'Percibe también la influencia que ejerce sobre ti y pon límites suaves donde tu deseo se nubla.',
    ichingMeaning:
      'La Influencia. La unión entre lo masculino y lo femenino. El éxito requiere que la influencia sea ejercida con receptividad y humildad, no con fuerza.',
  },
  32: {
    sephirah: 'Netzaj',
    meaning: 'Perseverancia, duración, fidelidad.',
    innerWork:
      'Elige qué vínculo, hábito o camino merece tu constancia y renueva un compromiso explícito con ello.',
    ichingMeaning:
      'La Duración. Perseverancia y constancia. Mantener el rumbo en el tiempo, sin dejarse llevar por las modas. El camino del medio es el camino del éxito.',
  },
  33: {
    sephirah: 'Guevurá',
    meaning: 'Retirada a tiempo, preservación de la fuerza.',
    innerWork:
      'Retírate de aquello que agota tu energía aunque te cueste ceder terreno en lo externo.',
    ichingMeaning:
      'La Retirada. Retirarse con dignidad y a tiempo. No es huida, sino preservación de la fuerza. El sabio sabe cuándo es el momento de ceder.',
  },
  34: {
    sephirah: 'Jojmá',
    meaning: 'Poder grande, impulso expansivo.',
    innerWork:
      'Asume tu potencia sin aplastar: decide un uso concreto, creativo y ético para tu fuerza ahora.',
    ichingMeaning:
      'El Poder de lo Grande. Gran fuerza que debe ser usada con ética y contención. No dejes que la potencia se convierta en arrogancia; la rectitud trae victoria.',
  },
  35: {
    sephirah: 'Jesed',
    meaning: 'Progreso, avance visible.',
    innerWork:
      'Reconoce objetivamente tu avance y define el siguiente pequeño paso que consolida lo logrado.',
    ichingMeaning:
      'El Progreso. Avance rápido y visible. La luz crece. La generosidad y la claridad son necesarias para aprovechar el momento.',
  },
  36: {
    sephirah: 'Biná',
    meaning: 'Retirada de la luz, protección del fuego.',
    innerWork:
      'Guarda tu brillo donde no es bien recibido y cultívalo en espacios íntimos de confianza.',
    ichingMeaning:
      'El Oscurecimiento de la Luz. Tiempos difíciles donde la virtud debe ser escondida. Cultiva tu luz interior en secreto y evita la confrontación directa.',
  },
  37: {
    sephirah: 'Tiferet',
    meaning: 'Corazón del hogar, calor afectivo.',
    innerWork:
      'Pregúntate qué tipo de hogar interno quieres ofrecer y empieza por cómo te hablas a ti mismo.',
    ichingMeaning:
      'La Familia. El Clan. La base del orden social y afectivo. La claridad de roles y la calidez del corazón son esenciales para la cohesión.',
  },
  38: {
    sephirah: 'Hod',
    meaning: 'Oposición, miradas distintas.',
    innerWork:
      'En lugar de convencer, trata de comprender la lógica del otro y qué te está espejando.',
    ichingMeaning:
      'La Oposición. Aislamiento y falta de entendimiento. Las diferencias son inevitables, pero el objetivo común debe ser el puente. No busques la confrontación.',
  },
  39: {
    sephirah: 'Guevurá',
    meaning: 'Obstáculo, bloqueo frontal.',
    innerWork:
      'Asume que el camino directo no es; busca la vuelta lateral en vez de volver a chocar de frente.',
    ichingMeaning:
      'El Obstáculo. La dificultad está delante. Es necesario detenerse, reflexionar sobre el camino y pedir ayuda si es necesario. Buscar el desvío.',
  },
  40: {
    sephirah: 'Jesed',
    meaning: 'Liberación, aflojamiento de la tensión.',
    innerWork:
      'Suelta al menos una deuda emocional que ya no quieres seguir cobrando, aunque el otro no cambie.',
    ichingMeaning:
      'La Liberación. El fin de la tensión. Desatar los nudos. El movimiento es hacia adelante una vez que se suelta la carga.',
  },
  41: {
    sephirah: 'Guevurá',
    meaning: 'Disminución voluntaria, simplificación.',
    innerWork:
      'Renuncia a algo pequeño pero real para cuidar algo más esencial que quieres preservar.',
    ichingMeaning:
      'La Disminución. Reducir lo superfluo para fortalecer lo esencial. Es un sacrificio voluntario que trae fortuna a largo plazo si se hace con sinceridad.',
  },
  42: {
    sephirah: 'Jesed',
    meaning: 'Aumento, bendición que crece.',
    innerWork:
      'Mientras algo aumenta, comparte una parte; así mantienes el flujo y la confianza en la abundancia.',
    ichingMeaning:
      'El Aumento. Momento de bendición y crecimiento. Es vital aprovechar esta energía para el bien de todos, compartiendo los beneficios.',
  },
  43: {
    sephirah: 'Jojmá',
    meaning: 'Verdad que irrumpe, decisión irreprimible.',
    innerWork:
      'Di lo que ya sabes con firmeza y sencillez, sin adornos ni violencia innecesaria.',
    ichingMeaning:
      'La Ruptura. La decisión irrevocable. La verdad se impone y debe ser comunicada con firmeza, pero sin violencia ni soberbia.',
  },
  44: {
    sephirah: 'Yesod',
    meaning: 'Encuentro magnético, tentación.',
    innerWork:
      'Reconoce el encanto sin entregarle el timón; observa qué parte vulnerable de ti responde a esa llamada.',
    ichingMeaning:
      'El Encuentro. La seducción sutil. Reconocer la tentación y los riesgos que conlleva el contacto con lo inesperado. Requiere control y prevención.',
  },
  45: {
    sephirah: 'Jesed',
    meaning: 'Reunión, convocatoria, comunidad.',
    innerWork:
      'Antes de pedir unión afuera, alinea tus partes internas y decide qué quieres convocar realmente.',
    ichingMeaning:
      'La Reunión. La congregación. Unirse en el centro para un objetivo común. La claridad en el liderazgo es esencial para evitar la dispersión.',
  },
  46: {
    sephirah: 'Netzaj',
    meaning: 'Ascenso gradual, esfuerzo constante.',
    innerWork:
      'Acepta subir lento: define un peldaño concreto que puedas subir esta semana sin agotarte.',
    ichingMeaning:
      'El Ascenso. Progreso gradual y constante. El éxito se construye paso a paso, con humildad y persistencia. La dirección es hacia arriba.',
  },
  47: {
    sephirah: 'Biná',
    meaning: 'Opresión, estrechez, agotamiento.',
    innerWork:
      'Nombra tu cansancio sin culpa y recorta algo antes de exigirte más rendimiento.',
    ichingMeaning:
      'El Agotamiento. La opresión. Estar atrapado en un estrecho límite. La clave es la constancia interior y la paciencia para esperar el cambio de la marea.',
  },
  48: {
    sephirah: 'Yesod',
    meaning: 'Pozo, fuente profunda de recursos.',
    innerWork:
      'Vuelve a tus aguas internas: prácticas, recuerdos y vínculos que te nutren de verdad.',
    ichingMeaning:
      'El Pozo. La fuente inagotable de vida. El pozo siempre está ahí, pero hay que saber usarlo y cuidarlo. Los recursos internos están disponibles.',
  },
  49: {
    sephirah: 'Hod',
    meaning: 'Revolución, cambio de forma.',
    innerWork:
      'Acepta que una versión tuya terminó; actualiza tu relato para acompañar la nueva piel.',
    ichingMeaning:
      'La Revolución. El cambio radical de viejas estructuras. Debe hacerse con el apoyo popular y la máxima ética, pues es un proceso violento.',
  },
  50: {
    sephirah: 'Biná',
    meaning: 'Vasija, estructura que contiene el fuego.',
    innerWork:
      'Revisa si tu “vasija” (cuerpo, casa, agenda) puede sostener el nivel de energía que deseas.',
    ichingMeaning:
      'La Vasija. El Caldero Sagrado. La estructura que contiene el alimento espiritual. Perfeccionar las formas y las herramientas para servir al propósito mayor.',
  },
  51: {
    sephirah: 'Jojmá',
    meaning: 'Trueno, impacto, despertar súbito.',
    innerWork:
      'Permite que el susto te despierte sin quedarte atrapado en la reacción defensiva.',
    ichingMeaning:
      'La Conmoción. El Trueno. Un impacto repentino que sacude. Acepta el miedo sin paralizarte; la acción debe ser simple y sincera para recuperar la calma.',
  },
  52: {
    sephirah: 'Maljut',
    meaning: 'Quietud del cuerpo, stop necesario.',
    innerWork:
      'Detén el movimiento externo y observa qué se agita adentro cuando todo afuera se inmoviliza.',
    ichingMeaning:
      'El Aquietamiento. La Montaña. Mantener la calma interna y detener el movimiento externo. La quietud mental es la base de la sabiduría.',
  },
  53: {
    sephirah: 'Netzaj',
    meaning: 'Desarrollo progresivo, maduración lenta.',
    innerWork:
      'Acepta la velocidad orgánica de tus procesos; registra tus avances en lugar de compararte.',
    ichingMeaning:
      'El Desarrollo. La Lenta Progresión. El avance debe ser gradual y metódico, como un árbol que crece. La paciencia es fundamental.',
  },
  54: {
    sephirah: 'Yesod',
    meaning: 'Unión desigual, deseo y destino.',
    innerWork:
      'Revisa dónde te colocas en segundo plano y si eso viene de amor o de poca autoestima.',
    ichingMeaning:
      'La Muchacha Casadera. Una unión con un desequilibrio de poder. Se requiere humildad y discreción, aceptando la situación actual sin buscar imponerse.',
  },
  55: {
    sephirah: 'Jesed',
    meaning: 'Abundancia intensa, plenitud.',
    innerWork:
      'Disfruta el momento pico sin aferrarte y usa una parte para sembrar futuro.',
    ichingMeaning:
      'La Plenitud. El punto máximo de la luz y la abundancia. Es un momento de gozo, pero la precaución es vital, ya que después del pico viene el descenso.',
  },
  56: {
    sephirah: 'Maljut',
    meaning: 'Andariego, no-raíz, viaje.',
    innerWork:
      'Acepta ser extranjero por un tiempo y arma un pequeño kit de cosas que te den hogar móvil.',
    ichingMeaning:
      'El Viajero. El forastero. Adaptarse a las circunstancias sin echar raíces profundas. La prudencia y la modestia son las mejores compañeras de viaje.',
  },
  57: {
    sephirah: 'Hod',
    meaning: 'Influencia sutil, viento mental.',
    innerWork:
      'Cuida las ideas que repites; son el viento que lentamente erosiona o pule tu paisaje interno.',
    ichingMeaning:
      'Lo Suave. El Viento. La influencia penetrante y sutil. La perseverancia en lo pequeño logra un cambio profundo. Es la fuerza que actúa desde abajo.',
  },
  58: {
    sephirah: 'Jesed',
    meaning: 'Gozo compartido, alegría.',
    innerWork:
      'Permítete disfrutar sin culpa, pero nota qué formas de placer te dejan realmente más vivo.',
    ichingMeaning:
      'La Alegría. El Lago. El gozo compartido que alimenta el espíritu. La comunicación abierta y sincera es la base de la felicidad.',
  },
  59: {
    sephirah: 'Biná',
    meaning: 'Disolución de rigideces, aflojar nudos.',
    innerWork:
      'Suaviza conscientemente una estructura o idea fija y observa qué aparece cuando cede.',
    ichingMeaning:
      'La Dispersión. Disolver las barreras y las rigideces. Es un momento de purificación para eliminar la separación. La fe y el desapego son necesarios.',
  },
  60: {
    sephirah: 'Guevurá',
    meaning: 'Límites, reglas, medida justa.',
    innerWork:
      'Define bordes claros de tiempo, energía y entrega para no resentirte después.',
    ichingMeaning:
      'La Restricción. Los Límites. Establecer medidas justas y necesarias para el crecimiento. Aceptar las limitaciones con sabiduría trae éxito.',
  },
  61: {
    sephirah: 'Tiferet',
    meaning: 'Verdad interior, corazón sincero.',
    innerWork:
      'Escucha tu verdad sin adornos y ajusta aunque sea un gesto externo para honrarla hoy.',
    ichingMeaning:
      'La Verdad Interior. La sinceridad que mueve montañas. La fe debe ser cultivada en el centro del ser; el corazón abierto trae la verdad.',
  },
  62: {
    sephirah: 'Hod',
    meaning: 'Preponderancia de lo pequeño, detalle.',
    innerWork:
      'Cuida los matices y los gestos mínimos; allí se juega ahora la diferencia real.',
    ichingMeaning:
      'La Preponderancia de lo Pequeño. Dar prioridad a los detalles y a las cosas modestas. Vuelos bajos y acción cautelosa, la grandeza está en lo pequeño.',
  },
  63: {
    sephirah: 'Tiferet',
    meaning: 'Después de la consumación, orden establecido.',
    innerWork:
      'Consolida lo logrado, corrige fugas pequeñas y evita iniciar algo enorme antes de integrar la experiencia.',
    ichingMeaning:
      'Después de la Consumación. El orden ya está establecido, pero la permanencia no es segura. Se requiere máxima precaución para mantener la estabilidad.',
  },
  64: {
    sephirah: 'Kéter',
    meaning: 'Umbral, casi-lleno, tensión creativa.',
    innerWork:
      'Acepta la incertidumbre del casi y mantén la presencia mientras el cierre madura por sí mismo.',
    ichingMeaning:
      'Antes de la Consumación. El umbral. El cambio está por completarse. La precipitación trae error; la paciencia en la incertidumbre garantiza el éxito.',
  },
};

// Sefirot base con color y clave
const SEFIROT_MAP = {
  Keter: {
    nombre: 'Kéter — Corona',
    clave: 'Origen, intención pura, voluntad esencial.',
    color: 'bg-indigo-100 border-indigo-300',
  },
  Hochmah: {
    nombre: 'Jojmá — Sabiduría',
    clave: 'Intuición repentina, visión global, chispa de comprensión.',
    color: 'bg-sky-100 border-sky-300',
  },
  Binah: {
    nombre: 'Biná — Entendimiento',
    clave: 'Estructurar, discernir, poner límites claros.',
    color: 'bg-rose-100 border-rose-300',
  },
  Hesed: {
    nombre: 'Jesed — Misericordia',
    clave: 'Expansión, confianza, generosidad y bendición.',
    color: 'bg-emerald-100 border-emerald-300',
  },
  Gevurah: {
    nombre: 'Guevurá — Rigor',
    clave: 'Juicio, corte sano, disciplina y límites.',
    color: 'bg-red-100 border-red-300',
  },
  Tiferet: {
    nombre: 'Tiferet — Belleza',
    clave: 'Equilibrio, corazón, coherencia entre lo interno y lo externo.',
    color: 'bg-amber-100 border-amber-300',
  },
  Netzach: {
    nombre: 'Netzaj — Victoria',
    clave: 'Deseo, perseverancia, impulso de avanzar.',
    color: 'bg-lime-100 border-lime-300',
  },
  Hod: {
    nombre: 'Hod — Gloria',
    clave: 'Lenguaje, mente, estrategia, análisis.',
    color: 'bg-violet-100 border-violet-300',
  },
  Yesod: {
    nombre: 'Yesod — Fundamento',
    clave: 'Inconsciente, vínculos, integración de fuerzas.',
    color: 'bg-cyan-100 border-cyan-300',
  },
  Malkuth: {
    nombre: 'Maljut — Reino',
    clave: 'Cuerpo, territorio, realidad concreta y cotidiana.',
    color: 'bg-slate-100 border-slate-300',
  },
};

// Niveles cabalísticos por línea mutante
const CABALISTIC_LINE_LEVELS = {
  1: {
    label: 'Línea 1 — Fundamento / Cuerpo',
    focus:
      'Inicio concreto del proceso: hábitos básicos, entorno físico, primera reacción instintiva.',
  },
  2: {
    label: 'Línea 2 — Vínculo / Emoción',
    focus:
      'Relación con el otro y contigo mismo en lo cotidiano: necesidades afectivas y seguridad emocional.',
  },
  3: {
    label: 'Línea 3 — Frontera / Prueba',
    focus:
      'Zona de fricción: límites, decisiones impulsivas, salir o quedarse en una situación.',
  },
  4: {
    label: 'Línea 4 — Puente / Camino',
    focus:
      'Transición: alianzas, ayuda, aprender a pedir apoyo y a confiar en el proceso.',
  },
  5: {
    label: 'Línea 5 — Autoridad / Corazón',
    focus:
      'Centro de decisión madura: liderazgo interno, ética, visión compasiva de lo que ocurre.',
  },
  6: {
    label: 'Línea 6 — Síntesis / Espíritu',
    focus:
      'Cierre de ciclo: soltar, integrar la experiencia, no forzar más de lo necesario.',
  },
};

// =======================
//   UTILIDADES
// =======================

const mapSephirahLabelToKey = (label = '') => {
  const t = label.toLowerCase();
  if (t.includes('kéter') || t.includes('keter')) return 'Keter';
  if (t.includes('jojmá') || t.includes('jojma') || t.includes('jojmá') || t.includes('jojmá'))
    return 'Hochmah';
  if (t.includes('biná') || t.includes('bina')) return 'Binah';
  if (t.includes('jesed') || t.includes('hesed')) return 'Hesed';
  if (t.includes('guevurá') || t.includes('guevura') || t.includes('gevurá')) return 'Gevurah';
  if (t.includes('tiferet')) return 'Tiferet';
  if (t.includes('netzaj') || t.includes('netzach')) return 'Netzach';
  if (t.includes('hod')) return 'Hod';
  if (t.includes('yesod')) return 'Yesod';
  if (t.includes('maljut') || t.includes('malkuth')) return 'Malkuth';
  return 'Malkuth';
};

// Devuelve toda la info unificada para un hexagrama: índice, datos cabalísticos + sefirah base
const getSefiraAssociation = (hexaCode) => {
  const raw = parseInt(hexaCode, 2);
  if (isNaN(raw)) {
    const base = SEFIROT_MAP.Malkuth;
    return {
      ...base,
      hexIndex: null,
      cabalaSephirah: 'Maljut (Reino)',
      cabalaMeaning: '',
      cabalaInnerWork: '',
      cabalaIchingMeaning: '',
    };
  }

  const hexIndex = raw + 1;
  const cabala = CABALA_HEXAGRAMAS[hexIndex];
  let key = 'Malkuth';

  if (cabala?.sephirah) {
    key = mapSephirahLabelToKey(cabala.sephirah);
  }

  const base = SEFIROT_MAP[key] || SEFIROT_MAP.Malkuth;

  return {
    ...base,
    hexIndex,
    cabalaSephirah: cabala?.sephirah || base.nombre,
    cabalaMeaning: cabala?.meaning || '',
    cabalaInnerWork: cabala?.innerWork || '',
    cabalaIchingMeaning: cabala?.ichingMeaning || '',
  };
};

// =======================
//   LÓGICA DEL I CHING
// =======================

/**
 * Tirada con 3 monedas:
 *   6 = Viejo Yin (0, mutante)
 *   7 = Joven Yang (1, fijo)
 *   8 = Joven Yin (0, fijo)
 *   9 = Viejo Yang (1, mutante)
 */
const performIChingThrow = () => {
  const lines = [];
  const mutations = [];
  const mutableLines = [];

  for (let i = 0; i < 6; i++) {
    const c1 = Math.random() < 0.5 ? 2 : 3;
    const c2 = Math.random() < 0.5 ? 2 : 3;
    const c3 = Math.random() < 0.5 ? 2 : 3;
    const throwValue = c1 + c2 + c3; // 6–9

    let line = '';
    let mutation = 0;

    if (throwValue === 6) {
      line = '0';
      mutation = 6;
    } else if (throwValue === 7) {
      line = '1';
      mutation = 0;
    } else if (throwValue === 8) {
      line = '0';
      mutation = 0;
    } else {
      line = '1';
      mutation = 9;
    }

    lines.push(line);
    mutations.push(mutation);

    let mutableLine = line;
    if (mutation === 6) mutableLine = '1';
    if (mutation === 9) mutableLine = '0';

    mutableLines.push(mutableLine);
  }

  return {
    lineas: lines, // índice 0 = línea 1 (abajo)
    mutaciones: mutations,
    lineasMutantes: mutableLines,
  };
};

// =======================
//  COMPONENTES DE UI
// =======================

const LineaIChing = ({ index, line, mutation }) => {
  const isYang = line === '1';
  const isMutable = mutation === 6 || mutation === 9;

  let lineContent;
  let mutationSymbol = '';
  let mutationColor = '';

  if (isYang) {
    lineContent = (
      <div className="flex justify-center items-center w-full">
        <div className="w-11/12 h-2 bg-indigo-700 rounded-full" />
      </div>
    );
    if (mutation === 9) {
      mutationSymbol = 'X';
      mutationColor = 'text-red-500';
    }
  } else {
    lineContent = (
      <div className="flex justify-center items-center w-full">
        <div className="w-5/12 h-2 bg-gray-700 rounded-full" />
        <div className="w-1/12 h-2 bg-white" />
        <div className="w-5/12 h-2 bg-gray-700 rounded-full" />
      </div>
    );
    if (mutation === 6) {
      mutationSymbol = 'O';
      mutationColor = 'text-yellow-600';
    }
  }

  return (
    <div className="flex items-center justify-center h-10 w-full relative">
      <span className="absolute left-0 text-xs font-mono text-gray-500">{index + 1}</span>
      {lineContent}
      <div
        className={`absolute right-0 w-6 h-6 flex items-center justify-center text-sm font-bold rounded-full ${
          isMutable ? 'border-2 border-current' : ''
        } ${mutationColor}`}
      >
        {mutationSymbol}
      </div>
    </div>
  );
};

// Llamada genérica al modelo Gemini
const API_URL =
  'https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent';

const callApi = async (systemPrompt, userPrompt) => {
  let response = null;
  let currentDelay = 1000;
  const maxRetries = 5;

  for (let i = 0; i < maxRetries; i++) {
    try {
      response = await fetch(API_URL, {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({
          contents: [{ parts: [{ text: userPrompt }] }],
          systemInstruction: { parts: [{ text: systemPrompt }] },
        }),
      });

      if (response.status === 429 && i < maxRetries - 1) {
        await new Promise((resolve) => setTimeout(resolve, currentDelay));
        currentDelay *= 2;
        continue;
      }

      if (!response.ok) {
        throw new Error(`Error HTTP: ${response.status}`);
      }

      const result = await response.json();
      const text = result.candidates?.[0]?.content?.parts?.[0]?.text;
      if (!text) throw new Error('Respuesta del modelo vacía o incompleta.');
      return text;
    } catch (err) {
      if (i === maxRetries - 1) throw err;
      console.warn(`Intento ${i + 1} fallido. Reintentando...`);
    }
  }
};

// =======================
//   APP PRINCIPAL
// =======================

const App = () => {
  const [result, setResult] = useState(null);
  const [interpretation, setInterpretation] = useState('');
  const [specificQuestion, setSpecificQuestion] = useState('');
  const [reflection, setReflection] = useState('');
  const [actionPlan, setActionPlan] = useState('');
  const [sefira, setSefira] = useState(null);

  const [loading, setLoading] = useState(false);
  const [reflectionLoading, setReflectionLoading] = useState(false);
  const [actionLoading, setActionLoading] = useState(false);
  const [error, setError] = useState(null);

  const generateInterpretation = async (primaryHexaCode, mutableHexaCode, mutations) => {
    if (!primaryHexaCode || !mutableHexaCode) return;

    setLoading(true);
    setInterpretation('');
    setError(null);

    const mutationDetails = mutations
      .map((m, i) =>
        m > 0
          ? `Línea ${i + 1} (${m}): ${
              m === 9 ? 'Yang Viejo (mutación a Yin)' : 'Yin Viejo (mutación a Yang)'
            }`
          : null,
      )
      .filter(Boolean)
      .join(', ');

    const associatedSefira = getSefiraAssociation(primaryHexaCode);
    setSefira(associatedSefira);

    const systemPrompt = `Eres un sabio consejero experto en el I Ching y la Cábala. Tu tarea es ofrecer una lectura completa y profunda en español, sin tono fatalista.
La respuesta debe ser en formato Markdown con este esquema exacto:

## ☯️ Interpretación del I Ching
(Explicación clara del Hexagrama Primario, el papel de las líneas mutantes y la dirección que indica el Hexagrama Mutante. Máximo 150 palabras).

## 🌳 Visión Cabalística
(Conecta el proceso descrito por los hexagramas con la Sefirá principal: ${
      associatedSefira.nombre
    }.
Ten en cuenta:
- Descripción cabalística para este hexagrama: "${associatedSefira.cabalaMeaning}"
- Trabajo interior sugerido: "${associatedSefira.cabalaInnerWork}"
- Síntesis clásica I Ching: "${associatedSefira.cabalaIchingMeaning}"

Usa el enfoque de esta Sefirá: "${associatedSefira.clave}" como eje para comprender lo que la persona está viviendo. Máximo 140 palabras).

Evita repetir literalmente estas frases, intégralas de manera orgánica. Tono cercano, reflexivo y responsable.`;

    const raw = parseInt(primaryHexaCode, 2);
    const hexIndex = isNaN(raw) ? null : raw + 1;

    const userQuery = `Realiza una lectura para:

- Hexagrama Primario (Inicial): ${primaryHexaCode} (número tradicional: ${
      hexIndex ?? '?'
    })
- Hexagrama Mutante (Secundario): ${mutableHexaCode}
- Líneas Mutantes: ${mutationDetails || 'No hay líneas mutantes.'}
- Sefirá central sugerida para este hexagrama: ${
      associatedSefira.cabalaSephirah
    } (${associatedSefira.nombre})

Indica claramente la relación entre el hexagrama primario y el mutante, usando una frase del tipo: "De X hacia Y".`;

    try {
      const text = await callApi(systemPrompt, userQuery);
      setInterpretation(text);
    } catch (e) {
      console.error('Fallo al generar la interpretación:', e);
      setError('No se pudo obtener la interpretación del I Ching. Intenta de nuevo.');
    } finally {
      setLoading(false);
    }
  };

  const generateReflection = async () => {
    if (!result || !specificQuestion.trim()) return;

    setReflectionLoading(true);
    setReflection('');
    setError(null);

    const associatedSefira = sefira || getSefiraAssociation(result.primaryHexaCode);

    const systemPrompt = `Eres un guía que integra I Ching y Cábala. Tu foco ahora es una reflexión aplicada a una pregunta concreta.
Responde en formato Markdown, máximo 160 palabras. Tono cercano y realista.`;

    const userQuery = `A partir de esta tirada:

- Hexagrama Primario: ${result.primaryHexaCode}
- Hexagrama Mutante: ${result.mutableHexaCode}
- Sefirá asociada: ${associatedSefira.cabalaSephirah} (${associatedSefira.nombre})
- Tema cabalístico: "${associatedSefira.cabalaMeaning}"
- Trabajo interior sugerido: "${associatedSefira.cabalaInnerWork}"

Pregunta específica de la persona: "${specificQuestion}"

Escribe una reflexión que:
1. Aplique el mensaje del hexagrama a esta pregunta puntual.
2. Use el enfoque de la Sefirá asociada como filtro (por ejemplo, si es Guevurá, enfatiza límites, cortes, claridad; si es Jesed, apertura, confianza, etc.).
3. No prometa resultados mágicos ni futuros garantizados.
4. Termine con una pregunta abierta para que la persona siga reflexionando.`;

    try {
      const text = await callApi(systemPrompt, userQuery);
      setReflection(text);
    } catch (e) {
      console.error('Fallo al generar la reflexión específica:', e);
      setError('No se pudo obtener la reflexión específica. Intenta de nuevo.');
    } finally {
      setReflectionLoading(false);
    }
  };

  const generateActionPlan = async () => {
    if (!result) return;

    setActionLoading(true);
    setActionPlan('');
    setError(null);

    const associatedSefira = sefira || getSefiraAssociation(result.primaryHexaCode);

    const systemPrompt = `Eres un maestro que integra la sabiduría del I Ching y la Cábala en prácticas concretas.
Debes responder en forma de lista Markdown (viñetas), máximo 10 ítems.`;

    const userQuery = `Diseña un pequeño plan de acción cabalístico basándote en:

- Hexagrama Primario: ${result.primaryHexaCode}
- Hexagrama Mutante: ${result.mutableHexaCode}
- Número tradicional del hexagrama primario: ${associatedSefira.hexIndex}
- Sefirá central: ${associatedSefira.cabalaSephirah} — ${associatedSefira.nombre}
- Tema cabalístico: "${associatedSefira.cabalaMeaning}"
- Trabajo interior sugerido: "${associatedSefira.cabalaInnerWork}"

Indicaciones:
- Da entre 4 y 8 acciones concretas, simples, que la persona pueda realizar en los próximos 7 días.
- Mezcla acciones externas (gestos, conversaciones, orden, decisiones) e internas (meditación breve, escritura, respiración, visualización sencilla).
- Cada punto debe ser breve (1–2 líneas) y comenzar con un verbo en infinitivo: "Observar...", "Escribir...", "Caminar...", etc.
- El tono debe ser realista, responsable y empoderador (no determinista ni fatalista).`;

    try {
      const text = await callApi(systemPrompt, userQuery);
      setActionPlan(text);
    } catch (e) {
      console.error('Fallo al generar el plan de acción:', e);
      setError('No se pudo obtener el plan de acción. Intenta de nuevo.');
    } finally {
      setActionLoading(false);
    }
  };

  const handleThrow = () => {
    const throwResult = performIChingThrow();
    const primaryHexaCode = throwResult.lineas.join('');
    const mutableHexaCode = throwResult.lineasMutantes.join('');

    const primaryIndex = parseInt(primaryHexaCode, 2);
    const mutableIndex = parseInt(mutableHexaCode, 2);

    const primaryName = `Hexagrama ${isNaN(primaryIndex) ? '?' : primaryIndex + 1}`;
    const mutableName = `Hexagrama ${isNaN(mutableIndex) ? '?' : mutableIndex + 1}`;

    const changingLines = throwResult.mutaciones
      .map((v, i) => (v === 6 || v === 9 ? { index: i + 1, value: v } : null))
      .filter(Boolean);
    const hasChangingLines = changingLines.length > 0;

    const baseResult = {
      ...throwResult,
      primaryHexaCode,
      mutableHexaCode,
      primaryName,
      mutableName,
      changingLines,
      hasChangingLines,
    };

    setResult(baseResult);
    setReflection('');
    setActionPlan('');
    setSpecificQuestion('');

    generateInterpretation(primaryHexaCode, mutableHexaCode, throwResult.mutaciones);
  };

  const renderMarkdown = (markdown) => {
    if (!markdown) return null;

    let html = markdown;

    html = html.replace(
      /^##\s*(.*)$/gm,
      '<h2 class="text-2xl font-bold mt-6 mb-3 text-indigo-700">$1</h2>',
    );

    html = html.replace(/^[-*]\s+(.*)$/gm, '<li class="ml-4 list-disc">$1</li>');
    html = html.replace(/(<li[\s\S]*?<\/li>)/gm, '<ul class="mb-2">$1</ul>');

    html = html.replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
    html = html.replace(/\*(.*?)\*/g, '<em>$1</em>');

    html = html.replace(/\n/g, '<br/>');

    return (
      <div
        className="markdown-body text-gray-700 leading-relaxed"
        dangerouslySetInnerHTML={{ __html: html }}
      />
    );
  };

  return (
    <div className="min-h-screen bg-gray-50 p-4 sm:p-8 flex justify-center items-start font-sans">
      <div className="w-full max-w-5xl bg-white shadow-2xl rounded-3xl p-6 sm:p-10 border border-indigo-200">
        <header className="text-center mb-8">
          <h1 className="text-4xl font-extrabold text-indigo-800">
            Oráculo I Ching &amp; Cábala
          </h1>
          <p className="text-gray-500 mt-2">
            Realiza una tirada. No necesitas formular una pregunta estricta: el Oráculo describe
            el estado del momento.
          </p>
        </header>

        <div className="flex justify-center mb-8">
          <button
            onClick={handleThrow}
            className="bg-green-600 text-white text-lg font-bold py-3 px-8 rounded-full shadow-lg hover:bg-green-700 transition duration-300 transform hover:scale-105 active:scale-95 disabled:opacity-50 flex items-center"
            disabled={loading}
          >
            {loading ? (
              <>
                <svg
                  className="animate-spin -ml-1 mr-3 h-5 w-5 text-white"
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                >
                  <circle
                    className="opacity-25"
                    cx="12"
                    cy="12"
                    r="10"
                    stroke="currentColor"
                    strokeWidth="4"
                  />
                  <path
                    className="opacity-75"
                    fill="currentColor"
                    d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"
                  />
                </svg>
                Consultando al Oráculo...
              </>
            ) : (
              <>
                <svg
                  className="w-6 h-6 mr-2"
                  fill="none"
                  stroke="currentColor"
                  viewBox="0 0 24 24"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    strokeLinecap="round"
                    strokeLinejoin="round"
                    strokeWidth="2"
                    d="M12 8v4m0 4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
                  />
                </svg>
                Realizar Nueva Tirada
              </>
            )}
          </button>
        </div>

        {error && (
          <div className="bg-red-100 border border-red-400 text-red-700 px-4 py-3 rounded relative mb-6">
            <strong className="font-bold">Error:</strong>
            <span className="block sm:inline ml-2">{error}</span>
          </div>
        )}

        {result && (
          <div className="mt-8 space-y-8">
            <div className="grid grid-cols-1 lg:grid-cols-3 gap-8">
              <div className="lg:col-span-2 grid md:grid-cols-2 gap-6">
                <div className="p-6 bg-indigo-50 rounded-2xl shadow-inner border border-indigo-200">
                  <h2 className="text-lg font-semibold text-gray-800 mb-1">
                    1. Hexagrama Primario (Inicial)
                  </h2>
                  <p className="text-sm text-indigo-600 font-mono mb-2">
                    Código: {result.primaryHexaCode}
                  </p>
                  <div className="flex flex-col items-center">
                    {result.lineas
                      .map((line, index) => (
                        <LineaIChing
                          key={index}
                          index={index}
                          line={line}
                          mutation={result.mutaciones[index]}
                        />
                      ))
                      .reverse()}
                  </div>
                  <div className="text-center mt-3 p-2 bg-indigo-200 rounded-lg font-bold text-indigo-800">
                    {result.primaryName}
                  </div>
                </div>

                <div className="p-6 bg-indigo-50 rounded-2xl shadow-inner border border-indigo-200">
                  <h2 className="text-lg font-semibold text-gray-800 mb-1">
                    2. Hexagrama Mutante (Resultado)
                  </h2>
                  <p className="text-sm text-indigo-600 font-mono mb-2">
                    Código: {result.mutableHexaCode}
                  </p>
                  <div className="flex flex-col items-center">
                    {result.lineasMutantes
                      .map((line, index) => (
                        <LineaIChing key={`mut-${index}`} index={index} line={line} mutation={0} />
                      ))
                      .reverse()}
                  </div>
                  <div className="text-center mt-3 p-2 bg-indigo-200 rounded-lg font-bold text-indigo-800">
                    {result.mutableName}
                  </div>
                </div>
              </div>

              <div
                className={`p-5 rounded-2xl shadow-lg border transition-all duration-300 ${
                  sefira ? sefira.color : 'bg-slate-100 border-slate-300'
                }`}
              >
                <h3 className="text-lg font-bold text-slate-800 mb-2">Enfoque Cabalístico</h3>
                <p className="text-sm font-semibold text-slate-700 mb-1">
                  {sefira?.cabalaSephirah}
                </p>
                <p className="text-xs text-slate-600 mb-3">{sefira?.nombre}</p>
                <p className="text-sm text-slate-700 mb-3">{sefira?.clave}</p>
                {sefira?.cabalaIchingMeaning && (
                  <>
                    <hr className="my-2 border-slate-300" />
                    <p className="text-xs font-semibold text-slate-700 mb-1">
                      Significado clásico I Ching
                    </p>
                    <p className="text-xs text-slate-700 mb-2">{sefira.cabalaIchingMeaning}</p>
                  </>
                )}
                {sefira?.cabalaInnerWork && (
                  <>
                    <p className="text-xs font-semibold text-slate-700 mt-1 mb-1">
                      Trabajo interior sugerido
                    </p>
                    <p className="text-xs text-slate-700">{sefira.cabalaInnerWork}</p>
                  </>
                )}
              </div>
            </div>

            <div className="p-6 bg-white rounded-2xl shadow-xl border border-gray-200">
              <h2 className="text-xl font-bold text-indigo-700 mb-4 border-b pb-2">
                Análisis Oracular
              </h2>

              {loading ? (
                <div className="text-center py-10 text-gray-500">
                  <svg
                    className="animate-spin mx-auto h-8 w-8 text-indigo-500 mb-3"
                    xmlns="http://www.w3.org/2000/svg"
                    fill="none"
                    viewBox="0 0 24 24"
                  >
                    <circle
                      className="opacity-25"
                      cx="12"
                      cy="12"
                      r="10"
                      stroke="currentColor"
                      strokeWidth="4"
                    />
                    <path
                      className="opacity-75"
                      fill="currentColor"
                      d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"
                    />
                  </svg>
                  Generando la sabiduría del I Ching y la perspectiva Cabalística...
                </div>
              ) : (
                interpretation && renderMarkdown(interpretation)
              )}

              {!loading && !interpretation && !error && (
                <div className="text-center py-10 text-gray-400 italic">
                  Presiona &quot;Realizar Nueva Tirada&quot; para obtener una lectura.
                </div>
              )}
            </div>

            {result.hasChangingLines && (
              <div className="p-6 bg-yellow-50 rounded-2xl shadow-md border border-yellow-200">
                <h3 className="text-lg font-semibold text-yellow-800 mb-3">Líneas Mutantes</h3>
                <ul className="space-y-3">
                  {result.changingLines.map((cl) => {
                    const type =
                      cl.value === 9
                        ? 'Viejo Yang (mutante a Yin)'
                        : 'Viejo Yin (mutante a Yang)';
                    const cabInfo = CABALISTIC_LINE_LEVELS[cl.index];
                    return (
                      <li
                        key={cl.index}
                        className="text-sm border-b border-yellow-200 pb-3 last:border-0"
                      >
                        <span className="font-bold text-yellow-900">Línea {cl.index}</span>{' '}
                        <span className="text-yellow-700">({type})</span>
                        {cabInfo && (
                          <div className="mt-2 text-xs text-yellow-900 space-y-1 pl-4 border-l-2 border-yellow-400/50">
                            <p className="font-semibold">{cabInfo.label}</p>
                            <p>{cabInfo.focus}</p>
                          </div>
                        )}
                      </li>
                    );
                  })}
                </ul>
              </div>
            )}

            <div className="grid md:grid-cols-2 gap-6">
              <div className="p-6 bg-slate-50 rounded-2xl shadow-md border border-slate-200">
                <h3 className="text-lg font-semibold text-slate-800 mb-2">
                  Pregunta Específica (Opcional)
                </h3>
                <p className="text-xs text-slate-500 mb-2">
                  Puedes escribir una situación o pregunta para profundizar la lectura desde tu
                  contexto actual.
                </p>
                <textarea
                  value={specificQuestion}
                  onChange={(e) => setSpecificQuestion(e.target.value)}
                  placeholder="Ejemplo: ¿Cómo puedo ordenar mi vida afectiva sin traicionarme a mí mismo?"
                  className="w-full h-24 p-3 border border-slate-300 rounded-lg text-sm focus:outline-none focus:ring-2 focus:ring-indigo-400 focus:border-indigo-400 resize-none"
                />
                <button
                  onClick={generateReflection}
                  disabled={!specificQuestion.trim() || reflectionLoading}
                  className="mt-3 bg-indigo-600 text-white text-sm font-semibold py-2 px-4 rounded-full shadow hover:bg-indigo-700 disabled:opacity-40 transition"
                >
                  {reflectionLoading ? 'Generando reflexión...' : 'Profundizar según mi pregunta'}
                </button>
              </div>

              <div className="p-6 bg-white rounded-2xl shadow-md border border-slate-200">
                <h3 className="text-lg font-semibold text-indigo-700 mb-2">
                  Reflexión Aplicada
                </h3>
                {reflectionLoading && (
                  <p className="text-sm text-slate-500 italic">
                    Abriendo espacio para una mirada más específica...
                  </p>
                )}
                {!reflectionLoading && reflection && renderMarkdown(reflection)}
                {!reflectionLoading && !reflection && (
                  <p className="text-sm text-slate-400 italic">
                    Escribe una pregunta arriba y pulsa &quot;Profundizar&quot; para recibir una
                    reflexión orientada.
                  </p>
                )}
              </div>
            </div>

            <div className="p-6 bg-amber-50 rounded-2xl shadow-md border border-amber-200">
              <div className="flex justify-between items-center mb-3">
                <h3 className="text-lg font-semibold text-amber-800">
                  Plan de Acción Cabalístico (7 días)
                </h3>
                <button
                  onClick={generateActionPlan}
                  disabled={actionLoading}
                  className="bg-amber-600 text-white text-xs font-semibold py-2 px-4 rounded-full shadow hover:bg-amber-700 disabled:opacity-40 transition"
                >
                  {actionLoading ? 'Creando plan...' : 'Sugerir acciones concretas'}
                </button>
              </div>
              {actionLoading && (
                <p className="text-sm text-amber-700 italic">
                  Elaborando un conjunto de gestos y prácticas sencillas para este ciclo...
                </p>
              )}
              {!actionLoading && actionPlan && renderMarkdown(actionPlan)}
              {!actionLoading && !actionPlan && (
                <p className="text-sm text-amber-700/80">
                  Aquí puedes recibir una lista de pequeños gestos y prácticas para encarnar el
                  mensaje de la tirada en tu vida diaria.
                </p>
              )}
            </div>
          </div>
        )}
      </div>
    </div>
  );
};

export default App;
