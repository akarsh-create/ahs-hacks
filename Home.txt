import React from "react";
import { Link } from "react-router-dom";
import { createPageUrl } from "@/utils";
import { Sprout, Sun, Droplets, BookOpen, TrendingUp, Heart, ArrowRight, Globe, Leaf, Recycle } from "lucide-react";
import { Button } from "@/components/ui/button";
import { motion } from "framer-motion";

export default function Home() {
  const features = [
    {
      icon: Sun,
      title: "Personalized Recommendations",
      description: "Get plant suggestions perfectly matched to your location, climate, and growing space"
    },
    {
      icon: Droplets,
      title: "Adaptive Care Guides",
      description: "Real-time care instructions that adapt to weather, season, and your plant's growth stage"
    },
    {
      icon: TrendingUp,
      title: "Growth Tracking",
      description: "Visual timeline tracking from seed to harvest with milestone reminders"
    },
    {
      icon: BookOpen,
      title: "Expert Resources",
      description: "Curated guides, recipes, and sustainability tips from trusted gardening sources"
    }
  ];

  return (
    <div className="min-h-screen bg-gradient-to-b from-[#E8F5E9] to-white">
      {/* Hero Section */}
      <section className="max-w-7xl mx-auto px-6 pt-16 md:pt-24 pb-20">
        <motion.div
          initial={{ opacity: 0, y: 20 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 0.6 }}
          className="text-center max-w-4xl mx-auto"
        >
          <div className="inline-flex items-center gap-2 bg-white/60 backdrop-blur-sm px-4 py-2 rounded-full mb-6 shadow-sm">
            <Heart className="w-4 h-4 text-[#3FA34D]" />
            <span className="text-sm font-medium text-[#1C1C1E]">Grow sustainably, eat fresh</span>
          </div>

          <h1 className="text-5xl md:text-7xl font-bold text-[#1C1C1E] mb-6 tracking-tight leading-tight">
            Grow food
            <span className="block text-[#3FA34D]">with confidence</span>
          </h1>

          <p className="text-xl md:text-2xl text-gray-600 mb-10 leading-relaxed max-w-2xl mx-auto">
            Your personal guide to sustainable micro-farming. From windowsill herbs to backyard harvests.
          </p>

          <div className="flex flex-col sm:flex-row gap-4 justify-center">
            <Link to={createPageUrl("Quiz")}>
              <Button 
                size="lg"
                className="bg-[#3FA34D] hover:bg-[#368F42] text-white h-14 px-8 text-lg font-medium rounded-xl shadow-lg hover:shadow-xl transition-all duration-300"
              >
                Get Started
                <ArrowRight className="ml-2 w-5 h-5" />
              </Button>
            </Link>
            <Link to={createPageUrl("Library")}>
              <Button 
                size="lg"
                variant="outline"
                className="h-14 px-8 text-lg font-medium rounded-xl border-2 border-[#3FA34D] text-[#3FA34D] hover:bg-[#E8F5E9] transition-all duration-300"
              >
                Explore Plants
              </Button>
            </Link>
          </div>
        </motion.div>
      </section>

      {/* Features Grid */}
      <section className="max-w-7xl mx-auto px-6 py-20">
        <motion.div
          initial={{ opacity: 0 }}
          animate={{ opacity: 1 }}
          transition={{ delay: 0.3, duration: 0.6 }}
        >
          <h2 className="text-3xl md:text-4xl font-bold text-[#1C1C1E] text-center mb-4">
            Everything you need to grow
          </h2>
          <p className="text-lg text-gray-600 text-center mb-12 max-w-2xl mx-auto">
            Simple, elegant tools designed to make gardening accessible for everyone
          </p>

          <div className="grid md:grid-cols-2 gap-6">
            {features.map((feature, index) => (
              <motion.div
                key={feature.title}
                initial={{ opacity: 0, y: 20 }}
                animate={{ opacity: 1, y: 0 }}
                transition={{ delay: 0.5 + index * 0.1, duration: 0.5 }}
                className="bg-white rounded-2xl p-8 shadow-sm hover:shadow-md transition-shadow duration-300 border border-gray-100"
              >
                <div className="w-14 h-14 bg-[#E8F5E9] rounded-xl flex items-center justify-center mb-5">
                  <feature.icon className="w-7 h-7 text-[#3FA34D]" />
                </div>
                <h3 className="text-xl font-semibold text-[#1C1C1E] mb-3">
                  {feature.title}
                </h3>
                <p className="text-gray-600 leading-relaxed">
                  {feature.description}
                </p>
              </motion.div>
            ))}
          </div>
        </motion.div>
      </section>

      {/* Sustainability Section */}
      <section className="max-w-7xl mx-auto px-6 py-20">
        <motion.div
          initial={{ opacity: 0, y: 20 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ delay: 0.6, duration: 0.6 }}
          className="bg-gradient-to-br from-green-50 via-emerald-50 to-teal-50 rounded-3xl p-8 md:p-16 border-2 border-[#3FA34D]/20"
        >
          <div className="text-center mb-12">
            <div className="inline-flex items-center gap-2 bg-[#3FA34D]/10 px-4 py-2 rounded-full mb-6">
              <Globe className="w-5 h-5 text-[#3FA34D]" />
              <span className="text-sm font-semibold text-[#3FA34D]">For Our Planet</span>
            </div>
            <h2 className="text-3xl md:text-5xl font-bold text-[#1C1C1E] mb-6">
              Growing more than food—
              <span className="block text-[#3FA34D]">growing hope</span>
            </h2>
            <p className="text-lg md:text-xl text-gray-700 leading-relaxed max-w-3xl mx-auto">
              Every seed you plant is a small act of rebellion against climate change. 
              Every herb you harvest is a victory over food waste. Every tomato you grow 
              is proof that change begins at home—one plant, one person, one garden at a time.
            </p>
          </div>

          <div className="grid md:grid-cols-3 gap-8">
            <div className="text-center">
              <div className="w-16 h-16 bg-white rounded-2xl flex items-center justify-center mx-auto mb-4 shadow-sm">
                <Recycle className="w-8 h-8 text-[#3FA34D]" />
              </div>
              <h3 className="text-xl font-bold text-[#1C1C1E] mb-3">Reduce Waste</h3>
              <p className="text-gray-700 leading-relaxed">
                No more plastic packaging, no transportation emissions. 
                Your food travels from soil to table in seconds, not thousands of miles.
              </p>
            </div>

            <div className="text-center">
              <div className="w-16 h-16 bg-white rounded-2xl flex items-center justify-center mx-auto mb-4 shadow-sm">
                <Leaf className="w-8 h-8 text-[#3FA34D]" />
              </div>
              <h3 className="text-xl font-bold text-[#1C1C1E] mb-3">Heal the Earth</h3>
              <p className="text-gray-700 leading-relaxed">
                Every plant you grow captures carbon, creates oxygen, and supports pollinators. 
                Your garden is a tiny ecosystem fighting for our future.
              </p>
            </div>

            <div className="text-center">
              <div className="w-16 h-16 bg-white rounded-2xl flex items-center justify-center mx-auto mb-4 shadow-sm">
                <Heart className="w-8 h-8 text-[#3FA34D]" />
              </div>
              <h3 className="text-xl font-bold text-[#1C1C1E] mb-3">Inspire Others</h3>
              <p className="text-gray-700 leading-relaxed">
                When your neighbors see fresh basil on your windowsill or strawberries on your balcony, 
                they'll realize they can do it too. Change spreads like seeds in the wind.
              </p>
            </div>
          </div>
        </motion.div>
      </section>

      {/* CTA Section */}
      <section className="max-w-7xl mx-auto px-6 py-20 pb-32 md:pb-20">
        <motion.div
          initial={{ opacity: 0, scale: 0.95 }}
          animate={{ opacity: 1, scale: 1 }}
          transition={{ delay: 0.8, duration: 0.5 }}
          className="bg-gradient-to-r from-[#3FA34D] to-[#89C27D] rounded-3xl p-12 md:p-16 text-center shadow-xl"
        >
          <Sprout className="w-16 h-16 text-white mx-auto mb-6" />
          <h2 className="text-3xl md:text-5xl font-bold text-white mb-6">
            Ready to start growing?
          </h2>
          <p className="text-xl text-white/90 mb-8 max-w-2xl mx-auto">
            Take our quick quiz to get personalized plant recommendations tailored to your space and experience
          </p>
          <Link to={createPageUrl("Quiz")}>
            <Button 
              size="lg"
              className="bg-white text-[#3FA34D] hover:bg-gray-50 h-14 px-10 text-lg font-semibold rounded-xl shadow-lg hover:shadow-xl transition-all duration-300"
            >
              Take the Quiz
              <ArrowRight className="ml-2 w-5 h-5" />
            </Button>
          </Link>
        </motion.div>
      </section>
    </div>
  );
}

