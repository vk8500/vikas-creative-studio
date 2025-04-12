# vikas-creative-studio
"A professional website for providing YouTube Automation, Video Editing, and related services. Designed to offer faceless video creation, scriptwriting, voiceovers, and more to help YouTubers grow their channels. The website is built with React, Tailwind CSS, and deployable via Vercel."
import React from "react";
import { Button } from "@/components/ui/button";
import { Card, CardContent } from "@/components/ui/card";
import { motion } from "framer-motion";
import { CheckCircle, Youtube, Video, Mic, Pencil } from "lucide-react";

export default function HomePage() {
  return (
    <div className="p-4 md:p-10 bg-[#0b0f1a] text-white min-h-screen font-sans">
      <header className="text-center mb-10">
        <h1 className="text-4xl md:text-6xl font-bold text-cyan-400 mb-4">
          Vikas Creative Studio
        </h1>
        <p className="text-lg md:text-xl text-gray-300">
          YouTube Automation & Video Editing Services
        </p>
        <Button className="mt-6 text-lg px-6 py-4 rounded-2xl shadow-md bg-cyan-500 hover:bg-cyan-400">
          Get a Free Demo
        </Button>
      </header>

      <section className="grid md:grid-cols-3 gap-6 mb-16">
        {services.map((service, index) => (
          <motion.div
            key={index}
            whileHover={{ scale: 1.05 }}
            className="bg-[#121829] p-6 rounded-2xl shadow-md border border-cyan-800"
          >
            <div className="flex items-center mb-4 text-cyan-400">
              {service.icon}
              <h3 className="text-xl font-semibold ml-3">{service.title}</h3>
            </div>
            <p className="text-gray-300 mb-4">{service.description}</p>
            <Button className="bg-cyan-600 hover:bg-cyan-500 w-full">Start Now</Button>
          </motion.div>
        ))}
      </section>

      <section className="bg-[#10141f] p-6 md:p-10 rounded-2xl shadow-md">
        <h2 className="text-3xl text-center font-bold text-cyan-300 mb-6">Our Packages</h2>
        <div className="grid md:grid-cols-3 gap-6">
          {packages.map((pkg, index) => (
            <Card key={index} className="bg-[#161b28] border border-cyan-800">
              <CardContent className="p-6 text-white">
                <h3 className="text-2xl font-semibold mb-2 text-cyan-400">{pkg.name}</h3>
                <p className="text-xl mb-4">₹{pkg.price}</p>
                <ul className="mb-4 space-y-2">
                  {pkg.features.map((f, idx) => (
                    <li key={idx} className="flex items-center text-gray-300">
                      <CheckCircle className="w-4 h-4 mr-2 text-green-400" /> {f}
                    </li>
                  ))}
                </ul>
                <Button className="bg-cyan-600 hover:bg-cyan-500 w-full">Choose Plan</Button>
              </CardContent>
            </Card>
          ))}
        </div>
      </section>
    </div>
  );
}

const services = [
  {
    title: "Faceless Video Creation",
    description: "AI scriptwriting, voiceover, and full video automation.",
    icon: <Video className="w-6 h-6" />,
  },
  {
    title: "YouTube Channel Setup",
    description: "SEO-optimized branding, automation setup, and monetization help.",
    icon: <Youtube className="w-6 h-6" />,
  },
  {
    title: "Podcast & Voiceover",
    description: "Professional podcast editing and AI/human voiceovers.",
    icon: <Mic className="w-6 h-6" />,
  },
  {
    title: "Script Writing",
    description: "Engaging scripts for YouTube, shorts, and faceless content.",
    icon: <Pencil className="w-6 h-6" />,
  },
];

const packages = [
  {
    name: "Starter Package",
    price: "4999",
    features: [
      "4 Faceless Videos (5 min each)",
      "AI Script + Voiceover",
      "Stock Footage + Thumbnail"
    ]
  },
  {
    name: "Pro Package",
    price: "9999",
    features: [
      "8 Videos",
      "Human-Touch Scripts",
      "Editing + SEO + Upload"
    ]
  },
  {
    name: "Ultimate Package",
    price: "19999",
    features: [
      "15+ Videos",
      "Human Voiceover",
      "Full Channel Management"
    ]
  }
];
