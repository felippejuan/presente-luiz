import React, { useState, useEffect, useRef } from 'react';
import { 
  Heart, 
  MapPin, 
  Calendar, 
  Printer, 
  Gift, 
  Volume2, 
  VolumeX, 
  ChevronRight
} from 'lucide-react';

// 1. Definições e Dados Pessoais (Totalmente personalizado para o casal)
const PARTNER_NAME = "Luiz Vitinho"; 
const SENDER_NAME = "Lippinho";
const SPA_NAME = "Buddha Spa";
const VOUCHER_CODE = "ZSSPPF3"; // Código exato da imagem enviada
const VOUCHER_VAL = "11/09/2026"; // Validade exata da imagem enviada
const PACKAGE_TITLE = "Mini Day Spa"; // Título exato do pacote

// Mensagem totalmente adaptada para o Luiz Vitinho
const ROMANTIC_MESSAGE = `Luiz Vitinho,

Eu sei o quanto você fica exausto com seus plantões (fisicamente e emocionalmente). Mesmo assim, você sempre chega em casa e fica presente comigo e com o Chiquinho.

Acho que nada seria mais simbólico do que te fazer desacelerar e de te presentear com um momento de autocuidado e descanso.

Te amo demais e espero que você aproveite bastante o presente.

Com carinho,
Lippinho`;

// Links de fotos pessoais do Cloudinary fornecidos pelo usuário
const PERSONAL_PHOTOS = [
  "https://res.cloudinary.com/diy4hbotq/image/upload/v1781216775/v2_06cba461-e677-4a02-98d1-2414064f5121_2_bxgdx0.jpg",
  "https://res.cloudinary.com/diy4hbotq/image/upload/v1781216771/20250717_212903_jtfi93.jpg",
  "https://res.cloudinary.com/diy4hbotq/image/upload/v1781216767/IMG-20260412-WA0175_ahi2v9.jpg",
  "https://res.cloudinary.com/diy4hbotq/image/upload/v1781216767/IMG-20260509-WA0158_gbtobu.jpg",
  "https://res.cloudinary.com/diy4hbotq/image/upload/v1781216767/IMG_9965_xlhf5d.jpg",
  "https://res.cloudinary.com/diy4hbotq/image/upload/v1781216767/IMG_9635_fvnoef.jpg",
  "https://res.cloudinary.com/diy4hbotq/image/upload/v1781216767/IMG-20250510-WA0050_udfl0z.jpg",
  "https://res.cloudinary.com/diy4hbotq/image/upload/v1781216766/IMG-20250809-WA0095_cqzqmt.jpg",
  "https://res.cloudinary.com/diy4hbotq/image/upload/v1781216766/IMG-20250418-WA0016_zmel42.jpg"
];

// Link direto e autêntico para a música "Amor I Love You" da Marisa Monte (hospedada no Archive.org)
const MUSIC_URL = "https://ia801509.us.archive.org/29/items/marisa-monte-amor-i-love-you/Marisa%20Monte%20-%20Amor%20I%20Love%20You.mp3"; 

export default function App() {
  const [isEnvelopeOpen, setIsEnvelopeOpen] = useState(false);
  const [isAudioPlaying, setIsAudioPlaying] = useState(false);
  const audioRef = useRef(null);
  
  // Ativa o autoplay na primeira interação do usuário na página
  useEffect(() => {
    const handleFirstInteraction = () => {
      if (!isAudioPlaying && audioRef.current) {
        audioRef.current.play()
          .then(() => setIsAudioPlaying(true))
          .catch(err => console.log("Autoplay aguardando interação direta do usuário."));
      }
      window.removeEventListener('click', handleFirstInteraction);
      window.removeEventListener('touchstart', handleFirstInteraction);
    };

    window.addEventListener('click', handleFirstInteraction);
    window.addEventListener('touchstart', handleFirstInteraction);

    return () => {
      window.removeEventListener('click', handleFirstInteraction);
      window.removeEventListener('touchstart', handleFirstInteraction);
    };
  }, [isAudioPlaying]);

  useEffect(() => {
    const link = document.createElement('link');
    link.href = 'https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,300&family=Montserrat:wght@200;300;400;500;600&display=swap';
    link.rel = 'stylesheet';
    document.head.appendChild(link);
  }, []);

  useEffect(() => {
    if (audioRef.current) {
      if (isAudioPlaying) {
        audioRef.current.play().catch(error => {
          console.log("Reprodução de mídia bloqueada temporariamente.", error);
          setIsAudioPlaying(false);
        });
      } else {
        audioRef.current.pause();
      }
    }
  }, [isAudioPlaying]);

  const toggleAudio = () => {
    setIsAudioPlaying(!isAudioPlaying);
  };

  const handlePrint = () => {
    window.print();
  };

  return (
    <div className="min-h-screen bg-[#FAF7F2] text-[#3E3B37] font-sans antialiased selection:bg-[#C5A059] selection:text-white pb-24 transition-colors duration-300">
      
      {/* Elemento de áudio da Marisa Monte */}
      <audio ref={audioRef} src={MUSIC_URL} loop />

      {/* Estilos customizados para impressão perfeita e limpa do Voucher */}
      <style>{`
        @media print {
          body * {
            visibility: hidden;
            background: white !important;
          }
          #printable-voucher-area, #printable-voucher-area * {
            visibility: visible;
          }
          #printable-voucher-area {
            position: absolute;
            left: 5%;
            top: 15%;
            width: 90%;
            border: 2px solid #E8DFD8 !important;
            padding: 30px !important;
            box-shadow: none !important;
            background: #FAF7F2 !important;
            -webkit-print-color-adjust: exact;
            print-color-adjust: exact;
            border-radius: 12px;
          }
          .no-print {
            display: none !important;
          }
        }
        .font-serif-lux {
          font-family: 'Cormorant Garamond', Georgia, serif;
        }
        .font-sans-lux {
          font-family: 'Montserrat', sans-serif;
        }
      `}</style>

      {/* HEADER / CONTROLE DE MÚSICA */}
      <nav className="sticky top-0 z-50 bg-[#FAF7F2]/90 backdrop-blur-md border-b border-[#E8DFD8] px-6 py-4 flex justify-between items-center no-print">
        <div className="flex items-center gap-2">
          <Heart className="w-5 h-5 text-[#C5A059] fill-[#C5A059]" />
          <span className="font-serif-lux text-xl tracking-widest uppercase text-[#3E3B37]">Amor e Calmaria — Para Luiz Vitinho</span>
        </div>
        
        <button
          onClick={toggleAudio}
          className="flex items-center gap-2 px-4 py-2 rounded-full border border-[#C5A059]/40 text-[#C5A059] hover:bg-[#C5A059] hover:text-white transition-all text-xs uppercase tracking-wider font-medium"
        >
          {isAudioPlaying ? <Volume2 className="w-4 h-4 animate-pulse" /> : <VolumeX className="w-4 h-4" />}
          <span className="font-sans-lux text-[11px] tracking-wide">
            {isAudioPlaying ? "Tocando: Amor I Love You" : "Ativar Trilha Sonora"}
          </span>
        </button>
      </nav>

      {/* HERO SECTION */}
      <section className="relative min-h-[85vh] flex flex-col justify-center items-center text-center px-6 overflow-hidden">
        <div className="absolute inset-0 z-0 opacity-20 pointer-events-none">
          <div className="absolute top-10 left-10 w-72 h-72 rounded-full bg-[#E8DFD8] filter blur-3xl"></div>
          <div className="absolute bottom-10 right-10 w-96 h-96 rounded-full bg-[#C5A059]/10 filter blur-3xl"></div>
        </div>

        <div className="relative z-10 max-w-4xl mx-auto space-y-8 animate-fade-in">
          <span className="text-[#C5A059] text-xs uppercase tracking-[0.3em] font-semibold block">
            Para Luiz Vitinho, preparado com carinho.
          </span>
          
          <h1 className="font-serif-lux text-5xl md:text-7xl font-light text-[#3E3B37] leading-tight">
            te amo <br className="hidden md:inline" /> 
            <span className="italic font-normal text-[#C5A059]">um infinito.</span>
          </h1>

          <div className="w-16 h-[1px] bg-[#C5A059] mx-auto my-6"></div>

          <p className="font-serif-lux text-xl md:text-2xl text-gray-500 max-w-2xl mx-auto font-light leading-relaxed">
            "Na tentativa de te surpreender e entregar seu presente com classe, bb."
          </p>

          <div className="pt-8">
            <a 
              href="#presente-section"
              className="inline-flex items-center gap-3 px-8 py-4 bg-[#3E3B37] text-[#FAF7F2] rounded-full hover:bg-[#C5A059] transition-all duration-300 text-xs uppercase tracking-[0.2em] font-medium shadow-md hover:shadow-lg hover:-translate-y-0.5"
            >
              Abrir seu Presente
              <ChevronRight className="w-4 h-4" />
            </a>
          </div>
        </div>

        <div className="absolute bottom-8 left-1/2 -translate-x-1/2 flex flex-col items-center gap-1.5 animate-bounce">
          <span className="text-[10px] uppercase tracking-widest text-[#8C8276]">Rolar</span>
          <div className="w-[1px] h-6 bg-[#C5A059]"></div>
        </div>
      </section>

      {/* GALERIA - NOSSOS MOMENTOS */}
      <section className="max-w-6xl mx-auto px-6 py-20 no-print">
        <div className="text-center max-w-2xl mx-auto mb-16">
          <span className="text-[#C5A059] text-xs uppercase tracking-widest font-semibold">lembranças</span>
          <h2 className="font-serif-lux text-4xl text-[#3E3B37] mt-2 font-light">Nossos Momentos</h2>
          <div className="w-12 h-[1px] bg-[#C5A059]/50 mx-auto mt-4 mb-4"></div>
          <p className="text-sm text-gray-500 leading-relaxed font-serif-lux italic text-base">
            "voltei nas fotos que temos desde março de 2025 e foi tão gostoso saber que vivi momentos muito felizes ao seu lado — e ansioso para viver muito mais!"
          </p>
        </div>

        {/* Grid de Fotos Pessoais */}
        <div className="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-3 gap-6">
          {PERSONAL_PHOTOS.map((photoUrl, index) => (
            <div key={index} className="relative aspect-[3/4] rounded-xl overflow-hidden shadow-sm group border border-[#E8DFD8]">
              <img 
                src={photoUrl} 
                alt={`Nossos momentos e histórias - Foto ${index + 1}`} 
                className="object-cover w-full h-full transition-transform duration-500 group-hover:scale-105"
              />
              <div className="absolute inset-0 bg-black/5 group-hover:bg-black/0 transition-colors pointer-events-none"></div>
            </div>
          ))}
        </div>
      </section>

      {/* SEÇÃO DA CARTA E REVELAÇÃO DO ENVELOPE */}
      <section id="presente-section" className="bg-[#E8DFD8]/40 py-24 px-6 relative overflow-hidden no-print">
        <div className="max-w-4xl mx-auto text-center">
          <span className="text-[#C5A059] text-xs uppercase tracking-[0.25em] font-bold">Momento de Revelação</span>
          <h2 className="font-serif-lux text-4xl md:text-5xl text-[#3E3B37] mt-3 mb-10 font-light">Abra o seu presente</h2>
          
          <div className="relative mx-auto max-w-xl">
            {!isEnvelopeOpen ? (
              // Envelope Fechado
              <div 
                onClick={() => setIsEnvelopeOpen(true)}
                className="cursor-pointer bg-white border-2 border-[#E8DFD8] p-8 md:p-12 rounded-2xl shadow-xl hover:shadow-2xl transition-all duration-500 transform hover:-translate-y-2 group"
              >
                <div className="absolute top-0 left-0 right-0 h-4 bg-[#C5A059]/10 rounded-t-2xl"></div>
                
                <div className="flex flex-col items-center justify-center py-12 space-y-6">
                  <div className="relative w-20 h-20 rounded-full bg-[#3E3B37] flex items-center justify-center shadow-lg group-hover:scale-110 transition-transform duration-500">
                    <Heart className="w-8 h-8 text-[#FAF7F2] fill-[#C5A059]" />
                    <div className="absolute inset-1.5 rounded-full border border-[#C5A059]/40"></div>
                  </div>

                  <div className="space-y-2">
                    <p className="font-serif-lux text-2xl text-[#3E3B37] italic font-medium">Para: {PARTNER_NAME}</p>
                    <p className="text-xs uppercase tracking-[0.15em] text-gray-400 font-sans-lux">Toque no selo para abrir</p>
                  </div>
                </div>
              </div>
            ) : (
              // Carta Aberta (Texto e Voucher Exato integrados sem poluição comercial)
              <div className="bg-[#FAF7F2] border-2 border-[#C5A059]/30 p-8 md:p-14 rounded-2xl shadow-2xl relative animate-fade-in text-left">
                <button 
                  onClick={() => setIsEnvelopeOpen(false)}
                  className="absolute top-4 right-4 text-xs tracking-wider text-[#8C8276] uppercase hover:text-[#C5A059] transition-colors"
                >
                  Fechar Carta
                </button>

                <div className="space-y-6">
                  <div className="flex items-center justify-between border-b border-[#E8DFD8] pb-4">
                    <span className="font-serif-lux text-xl italic text-[#C5A059]">Para: {PARTNER_NAME}</span>
                    <Heart className="w-5 h-5 text-[#C5A059] fill-[#C5A059]" />
                  </div>

                  <p className="font-serif-lux text-lg md:text-xl text-[#3E3B37] leading-relaxed font-light whitespace-pre-line italic">
                    {ROMANTIC_MESSAGE}
                  </p>

                  {/* O BLOCO EXATO DO SEU VOUCHER ("AQUILO DALI EM CIMA") */}
                  <div className="pt-8 border-t border-[#E8DFD8] space-y-4">
                    <span className="block text-[11px] uppercase tracking-wider text-gray-400 font-sans-lux font-semibold">
                      Seu Voucher de Acesso:
                    </span>
                    
                    <div 
                      id="printable-voucher-area"
                      className="text-left font-sans space-y-1 p-5 rounded-2xl border-2 border-[#C5A059]/30 bg-white max-w-sm shadow-sm"
                    >
                      <p className="font-semibold text-gray-700 text-[16px] tracking-wide uppercase font-sans-lux">{PACKAGE_TITLE}</p>
                      <p className="text-[#8B0000] font-medium text-[13px] flex justify-between gap-6 pt-1">
                        <span>Val. {VOUCHER_VAL}</span>
                        <span className="font-mono">Cód: {VOUCHER_CODE}</span>
                      </p>
                    </div>

                    {/* Botão de download rápido do voucher em PDF */}
                    <div className="pt-2">
                      <button
                        onClick={handlePrint}
                        className="px-5 py-2.5 bg-[#C5A059] text-white rounded-lg hover:bg-[#B38F4B] transition-all text-xs uppercase tracking-widest font-bold flex items-center gap-2 shadow-sm"
                      >
                        <Printer className="w-3.5 h-3.5" /> Salvar Voucher (PDF)
                      </button>
                    </div>
                  </div>
                </div>
              </div>
            )}
          </div>
        </div>
      </section>

      {/* HIGHLIGHTS DA EXPERIÊNCIA DO SPA (Com a imagem Jardins-03_jt947v.jpg) */}
      <section className="py-24 max-w-6xl mx-auto px-6 no-print">
        <div className="grid grid-cols-1 md:grid-cols-2 gap-16 items-center">
          <div className="space-y-8">
            <span className="text-[#C5A059] text-xs uppercase tracking-widest font-semibold block">O que espera por você</span>
            <h3 className="font-serif-lux text-4xl text-[#3E3B37] font-light leading-tight">
              Uma jornada completa de reconexão sensorial e calma profunda.
            </h3>
            <p className="text-sm text-gray-500 leading-relaxed">
              O {PACKAGE_TITLE} no {SPA_NAME} foi minuciosamente planejado para oferecer uma experiência de desligamento total do cotidiano. Da entrada à saída, cada momento é focado no bem-estar integral.
            </p>

            <div className="space-y-6">
              <div className="flex gap-4">
                <span className="font-serif-lux text-xl text-[#C5A059] font-semibold">01.</span>
                <div>
                  <h5 className="font-semibold text-sm uppercase tracking-wider text-[#3E3B37]">Relaxante Corporal 60 minutos *</h5>
                  <p className="text-xs text-gray-500 mt-1">Massagem anti-estresse aplicada com óleos. Terapia realizada em todo o corpo, combinando movimentos de deslizamento, amassamento, rolamento e percussão.<br/>*Ou 50 minutos, conforme disponibilidade de cada unidade.</p>
                </div>
              </div>

              <div className="flex gap-4">
                <span className="font-serif-lux text-xl text-[#C5A059] font-semibold">02.</span>
                <div>
                  <h5 className="font-semibold text-sm uppercase tracking-wider text-[#3E3B37]">Banho de Imersão Individual (20 a 30min)</h5>
                  <p className="text-xs text-gray-500 mt-1">O Banho de imersão é altamente relaxante e utiliza água na temperatura de 38º a 40º C, preparada com sais de banho e pétalas de rosas. As tinas podem ser de madeira ou de PVC, conforme disponibilidade de cada unidade. Todos os banhos são acompanhados de taça de vinho e castanhas.</p>
                </div>
              </div>

              <div className="flex gap-4">
                <span className="font-serif-lux text-xl text-[#C5A059] font-semibold">03.</span>
                <div>
                  <h5 className="font-semibold text-sm uppercase tracking-wider text-[#3E3B37]">Acesso às Áreas de Relaxamento</h5>
                  <p className="text-xs text-gray-500 mt-1">Livre trânsito e recepção para desfrutar da quietude e o silêncio confortável do local.</p>
                </div>
              </div>
            </div>
          </div>

          {/* Imagem do spa atualizada para Jardins-03_jt947v.jpg */}
          <div className="relative">
            <div className="absolute inset-4 border border-[#C5A059] z-10 translate-x-3 translate-y-3 pointer-events-none"></div>
            <div className="aspect-[4/5] bg-[#E8DFD8] overflow-hidden shadow-xl">
              <img 
                src="https://res.cloudinary.com/diy4hbotq/image/upload/v1781285134/Jardins-03_jt947v.jpg" 
                alt="Área de Relaxamento Jardins Buddha Spa" 
                className="w-full h-full object-cover"
              />
            </div>
          </div>
        </div>
      </section>

      {/* FOOTER */}
      <footer className="mt-20 border-t border-[#E8DFD8] pt-12 text-center text-gray-400 text-xs tracking-wider space-y-4 no-print">
        <p className="font-serif-lux italic text-lg text-[#3E3B37]">
          "Te amo um infinito."
        </p>
        <p className="uppercase text-[9px] text-gray-400">
          Feito sob medida por {SENDER_NAME} para {PARTNER_NAME} • 2026
        </p>
      </footer>
    </div>
  );
}
