# -Portfolio_Patrick
import { useEffect, useState } from "react";
import { motion } from "framer-motion";
import { Moon, Sun } from "lucide-react";
import "./index.css";

export default function App() {
  const [darkMode, setDarkMode] = useState(false);
  const [scrollProgress, setScrollProgress] = useState(0);

  useEffect(() => {
    const handleScroll = () => {
      const totalScroll = document.documentElement.scrollTop;
      const windowHeight =
        document.documentElement.scrollHeight -
        document.documentElement.clientHeight;
      const scroll = `${(totalScroll / windowHeight) * 100}`;
      setScrollProgress(scroll);
    };
    window.addEventListener("scroll", handleScroll);
    return () => window.removeEventListener("scroll", handleScroll);
  }, []);

  return (
    <div className={darkMode ? "dark" : ""}>
      <div className="bg-white dark:bg-gray-900 text-gray-900 dark:text-white min-h-screen transition-colors duration-300">
        <motion.div
          className="fixed top-0 left-0 h-1 bg-indigo-500 z-50"
          style={{ width: `${scrollProgress}%` }}
          initial={{ width: 0 }}
          animate={{ width: `${scrollProgress}%` }}
        />

        <header className="p-6 text-center bg-indigo-600 text-white rounded-b-2xl shadow-xl">
          <h1 className="text-3xl md:text-4xl font-bold">
            🎨 Portfólio do Patrick Barreto – Dev em Ascensão 🌱💻
          </h1>
          <button
            onClick={() => setDarkMode(!darkMode)}
            className="absolute top-4 right-4 p-2 rounded-full bg-indigo-800 hover:bg-indigo-700"
            aria-label="Toggle Dark Mode"
          >
            {darkMode ? <Sun size={20} /> : <Moon size={20} />}
          </button>
        </header>

        <main className="max-w-3xl mx-auto p-6 space-y-10">
          <section>
            <h2 className="text-indigo-600 text-2xl font-bold mb-2">👨‍💻 Sobre Mim</h2>
            <p className="italic mb-2">"Entre bits e sonhos, eu sou o erro 404 que virou solução."</p>
            <p>
              Sou o Patrick, um jovem de 20 anos desbravando o código da vida enquanto
              curso Ciência da Computação na FIB Bauru. Me reinvento entre as linhas de código e os desafios
              da realidade. Apaixonado por tecnologia, curioso por natureza e faminto por evolução.
            </p>
            <p>
              Namoro a Vitoria, minha player 2, e junto dela busco subir de nível não só como dev,
              mas como ser humano.
            </p>
          </section>

          <section>
            <h2 className="text-indigo-600 text-2xl font-bold mb-2">🛠️ Habilidades</h2>
            <p className="italic mb-2">"A lógica é minha espada, a criatividade meu escudo."</p>
            <ul className="list-disc list-inside space-y-1">
              <li><strong>Linguagens:</strong> Python, JavaScript, Java, C</li>
              <li><strong>Web:</strong> HTML, CSS</li>
              <li><strong>Banco de Dados:</strong> MySQL</li>
              <li><strong>Ferramentas:</strong> Git, GitHub, VS Code, Figma</li>
              <li><strong>Estudando agora:</strong> Banco de Dados, SQL Server</li>
            </ul>
          </section>

          <section>
            <h2 className="text-indigo-600 text-2xl font-bold mb-2">🚀 Projetos</h2>
            <p className="italic mb-2">"Cada projeto é um grito do meu potencial querendo ser ouvido."</p>
            <ul className="list-disc list-inside space-y-2">
              <li>
                <strong>🕹️ Gamezinho:</strong> Mini game 2D com obstáculos aleatórios. <a href="Mosquito.apk" download className="text-indigo-500 hover:underline">📥 Baixar APK</a>
              </li>
              <li><strong>🌐 Site Pessoal:</strong> Feito com React + Tailwind, responsivo e estiloso.</li>
              <li><strong>📊 Dashboard de Finanças:</strong> Calculadora de despesas e entradas com gráficos Chart.js.</li>
            </ul>
          </section>

          <section>
            <h2 className="text-indigo-600 text-2xl font-bold mb-2">📈 Objetivos</h2>
            <p className="italic mb-2">"Não busco só um trampo, busco um propósito."</p>
            <ul className="list-disc list-inside space-y-1">
              <li>Conseguir meu primeiro estágio na área de tech</li>
              <li>Contribuir em projetos reais com impacto social</li>
              <li>Crescer como dev, como homem e como mente pensante</li>
              <li>Me tornar referência pra quem acha que não é possível</li>
            </ul>
          </section>

          <section>
            <h2 className="text-indigo-600 text-2xl font-bold mb-2">📫 Contato</h2>
            <p className="italic mb-2">"Se curtir minha vibe, bora construir junto."</p>
            <ul className="space-y-2">
              <li><a href="mailto:patrickhenriquebarreto@gmail.com" className="text-indigo-500 hover:underline">📧 Email: patrickhenriquebarreto@gmail.com</a></li>
              <li><a href="https://www.linkedin.com/in/patrick-barreto-242449245/" target="_blank" className="text-indigo-500 hover:underline">💼 LinkedIn</a></li>
              <li><a href="https://github.com/PkHAB" target="_blank" className="text-indigo-500 hover:underline">🐙 GitHub</a></li>
              <li><a href="https://instagram.com/pk__barreto" target="_blank" className="text-indigo-500 hover:underline">📱 Instagram: @pk__barreto</a></li>
            </ul>
          </section>
        </main>
      </div>
    </div>
  );
}
