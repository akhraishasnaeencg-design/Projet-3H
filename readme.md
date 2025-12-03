import React, { useState } from 'react';
import { BarChart, Bar, LineChart, Line, PieChart, Pie, Cell, XAxis, YAxis, CartesianGrid, Tooltip, Legend, ResponsiveContainer } from 'recharts';
import { TrendingUp, Users, DollarSign, MapPin, Award, BookOpen } from 'lucide-react';

const EngineeringJobsAnalysis = () => {
  const [activeTab, setActiveTab] = useState('overview');

  // Données simulées basées sur des analyses typiques des métiers de l'ingénierie
  const salaryBySpecialty = [
    { specialite: 'IA/ML', salaireMoyen: 95000, nombre: 450 },
    { specialite: 'Data Science', salaireMoyen: 88000, nombre: 520 },
    { specialite: 'DevOps', salaireMoyen: 82000, nombre: 380 },
    { specialite: 'Cybersécurité', salaireMoyen: 85000, nombre: 290 },
    { specialite: 'Cloud', salaireMoyen: 83000, nombre: 410 },
    { specialite: 'Full Stack', salaireMoyen: 75000, nombre: 680 },
    { specialite: 'Mobile', salaireMoyen: 72000, nombre: 340 },
    { specialite: 'Embedded', salaireMoyen: 78000, nombre: 250 }
  ];

  const experienceDistribution = [
    { experience: '0-2 ans', count: 850, salaire: 52000 },
    { experience: '3-5 ans', count: 1200, salaire: 72000 },
    { experience: '6-10 ans', count: 980, salaire: 95000 },
    { experience: '11-15 ans', count: 520, salaire: 115000 },
    { experience: '15+ ans', count: 270, salaire: 130000 }
  ];

  const locationData = [
    { ville: 'Paris', offres: 1450, salaireMoyen: 85000 },
    { ville: 'Lyon', offres: 580, salaireMoyen: 72000 },
    { ville: 'Toulouse', offres: 420, salaireMoyen: 68000 },
    { ville: 'Nantes', offres: 380, salaireMoyen: 66000 },
    { ville: 'Bordeaux', offres: 350, salaireMoyen: 65000 },
    { ville: 'Lille', offres: 290, salaireMoyen: 64000 }
  ];

  const contractTypes = [
    { type: 'CDI', value: 72, count: 2520 },
    { type: 'CDD', value: 15, count: 525 },
    { type: 'Freelance', value: 10, count: 350 },
    { type: 'Alternance', value: 3, count: 105 }
  ];

  const skillsDemand = [
    { competence: 'Python', demande: 85 },
    { competence: 'JavaScript', demande: 78 },
    { competence: 'Java', demande: 72 },
    { competence: 'SQL', demande: 68 },
    { competence: 'AWS', demande: 65 },
    { competence: 'Docker', demande: 62 },
    { competence: 'Git', demande: 90 },
    { competence: 'React', demande: 58 }
  ];

  const COLORS = ['#3b82f6', '#8b5cf6', '#ec4899', '#f59e0b', '#10b981', '#6366f1'];

  const StatCard = ({ icon: Icon, title, value, subtitle, color }) => (
    <div className="bg-white rounded-lg shadow-md p-6 border-l-4" style={{ borderColor: color }}>
      <div className="flex items-center justify-between">
        <div>
          <p className="text-gray-500 text-sm font-medium">{title}</p>
          <p className="text-2xl font-bold mt-2">{value}</p>
          <p className="text-gray-400 text-xs mt-1">{subtitle}</p>
        </div>
        <Icon className="text-gray-400" size={32} />
      </div>
    </div>
  );

  return (
    <div className="min-h-screen bg-gray-50 p-6">
      <div className="max-w-7xl mx-auto">
        {/* En-tête */}
        <div className="bg-gradient-to-r from-blue-600 to-purple-600 rounded-lg shadow-lg p-8 mb-8 text-white">
          <h1 className="text-4xl font-bold mb-4">Analyse des Métiers de l'Ingénierie</h1>
          <p className="text-blue-100 text-lg">
            Compte rendu détaillé des tendances, salaires et compétences recherchées
          </p>
        </div>

        {/* Navigation par onglets */}
        <div className="bg-white rounded-lg shadow-md mb-6 p-1">
          <div className="flex gap-2">
            {['overview', 'salaires', 'competences', 'geographie'].map((tab) => (
              <button
                key={tab}
                onClick={() => setActiveTab(tab)}
                className={`flex-1 py-3 px-4 rounded-md font-medium transition-colors ${
                  activeTab === tab
                    ? 'bg-blue-600 text-white'
                    : 'bg-gray-50 text-gray-600 hover:bg-gray-100'
                }`}
              >
                {tab === 'overview' && 'Vue d\'ensemble'}
                {tab === 'salaires' && 'Salaires'}
                {tab === 'competences' && 'Compétences'}
                {tab === 'geographie' && 'Géographie'}
              </button>
            ))}
          </div>
        </div>

        {/* Vue d'ensemble */}
        {activeTab === 'overview' && (
          <div className="space-y-6">
            <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
              <StatCard
                icon={Users}
                title="Offres analysées"
                value="3,500+"
                subtitle="Postes d'ingénieurs"
                color="#3b82f6"
              />
              <StatCard
                icon={DollarSign}
                title="Salaire médian"
                value="78,000€"
                subtitle="Par an"
                color="#8b5cf6"
              />
              <StatCard
                icon={TrendingUp}
                title="Croissance"
                value="+18%"
                subtitle="Sur 12 mois"
                color="#10b981"
              />
              <StatCard
                icon={MapPin}
                title="Villes couvertes"
                value="25+"
                subtitle="En France"
                color="#f59e0b"
              />
            </div>

            <div className="bg-white rounded-lg shadow-md p-6">
              <h2 className="text-2xl font-bold mb-4 flex items-center gap-2">
                <Award className="text-blue-600" />
                Distribution par Type de Contrat
              </h2>
              <p className="text-gray-600 mb-6">
                Répartition des offres selon le type de contrat proposé
              </p>
              <ResponsiveContainer width="100%" height={300}>
                <PieChart>
                  <Pie
                    data={contractTypes}
                    cx="50%"
                    cy="50%"
                    labelLine={false}
                    label={({ type, value }) => `${type}: ${value}%`}
                    outerRadius={100}
                    fill="#8884d8"
                    dataKey="value"
                  >
                    {contractTypes.map((entry, index) => (
                      <Cell key={`cell-${index}`} fill={COLORS[index % COLORS.length]} />
                    ))}
                  </Pie>
                  <Tooltip />
                </PieChart>
              </ResponsiveContainer>
              <div className="mt-4 p-4 bg-blue-50 rounded-lg">
                <p className="text-sm text-gray-700">
                  <strong>💡 Analyse :</strong> Le CDI domine largement le marché avec 72% des offres, 
                  confirmant la stabilité recherchée dans le secteur de l'ingénierie. Le freelance représente 
                  10% des opportunités, une part en croissance reflétant la flexibilité croissante du marché.
                </p>
              </div>
            </div>

            <div className="bg-white rounded-lg shadow-md p-6">
              <h2 className="text-2xl font-bold mb-4 flex items-center gap-2">
                <TrendingUp className="text-purple-600" />
                Distribution par Niveau d'Expérience
              </h2>
              <p className="text-gray-600 mb-6">
                Nombre d'offres et salaires moyens selon l'expérience
              </p>
              <ResponsiveContainer width="100%" height={350}>
                <BarChart data={experienceDistribution}>
                  <CartesianGrid strokeDasharray="3 3" />
                  <XAxis dataKey="experience" />
                  <YAxis yAxisId="left" />
                  <YAxis yAxisId="right" orientation="right" />
                  <Tooltip />
                  <Legend />
                  <Bar yAxisId="left" dataKey="count" fill="#3b82f6" name="Nombre d'offres" />
                  <Bar yAxisId="right" dataKey="salaire" fill="#8b5cf6" name="Salaire moyen (€)" />
                </BarChart>
              </ResponsiveContainer>
              <div className="mt-4 p-4 bg-purple-50 rounded-lg">
                <p className="text-sm text-gray-700">
                  <strong>💡 Analyse :</strong> Les profils juniors et intermédiaires (3-5 ans) sont les plus 
                  recherchés avec 1,200 offres. On observe une progression salariale cohérente : +38% entre 0-2 ans 
                  et 3-5 ans, puis +32% vers 6-10 ans. Les seniors (15+) bénéficient d'une prime d'expérience significative.
                </p>
              </div>
            </div>
          </div>
        )}

        {/* Onglet Salaires */}
        {activeTab === 'salaires' && (
          <div className="space-y-6">
            <div className="bg-white rounded-lg shadow-md p-6">
              <h2 className="text-2xl font-bold mb-4 flex items-center gap-2">
                <DollarSign className="text-green-600" />
                Salaires Moyens par Spécialité
              </h2>
              <p className="text-gray-600 mb-6">
                Comparaison des rémunérations annuelles brutes selon les domaines d'expertise
              </p>
              <ResponsiveContainer width="100%" height={400}>
                <BarChart data={salaryBySpecialty} layout="vertical">
                  <CartesianGrid strokeDasharray="3 3" />
                  <XAxis type="number" />
                  <YAxis dataKey="specialite" type="category" width={120} />
                  <Tooltip />
                  <Legend />
                  <Bar dataKey="salaireMoyen" fill="#10b981" name="Salaire moyen (€)" />
                </BarChart>
              </ResponsiveContainer>
              <div className="mt-4 p-4 bg-green-50 rounded-lg">
                <p className="text-sm text-gray-700">
                  <strong>💡 Analyse :</strong> L'IA/ML arrive en tête avec 95,000€ en moyenne, reflétant la forte 
                  demande pour ces compétences stratégiques. La Data Science et la Cybersécurité suivent de près. 
                  L'écart entre les spécialités les mieux et les moins rémunérées atteint 23,000€, montrant une 
                  différenciation claire du marché selon l'expertise.
                </p>
              </div>
            </div>

            <div className="bg-white rounded-lg shadow-md p-6">
              <h2 className="text-2xl font-bold mb-4">Nombre d'Offres par Spécialité</h2>
              <p className="text-gray-600 mb-6">
                Volume de recrutement selon les domaines techniques
              </p>
              <ResponsiveContainer width="100%" height={350}>
                <BarChart data={salaryBySpecialty}>
                  <CartesianGrid strokeDasharray="3 3" />
                  <XAxis dataKey="specialite" angle={-45} textAnchor="end" height={100} />
                  <YAxis />
                  <Tooltip />
                  <Bar dataKey="nombre" fill="#3b82f6" name="Nombre d'offres" />
                </BarChart>
              </ResponsiveContainer>
              <div className="mt-4 p-4 bg-blue-50 rounded-lg">
                <p className="text-sm text-gray-700">
                  <strong>💡 Analyse :</strong> Le développement Full Stack domine le marché avec 680 offres, 
                  suivi de la Data Science (520) et de l'IA/ML (450). Cette tendance montre que malgré des salaires 
                  plus élevés pour les spécialités émergentes, les postes généralistes restent les plus demandés.
                </p>
              </div>
            </div>
          </div>
        )}

        {/* Onglet Compétences */}
        {activeTab === 'competences' && (
          <div className="space-y-6">
            <div className="bg-white rounded-lg shadow-md p-6">
              <h2 className="text-2xl font-bold mb-4 flex items-center gap-2">
                <BookOpen className="text-indigo-600" />
                Compétences les Plus Demandées
              </h2>
              <p className="text-gray-600 mb-6">
                Pourcentage d'offres mentionnant chaque compétence technique
              </p>
              <ResponsiveContainer width="100%" height={400}>
                <BarChart data={skillsDemand} layout="vertical">
                  <CartesianGrid strokeDasharray="3 3" />
                  <XAxis type="number" domain={[0, 100]} />
                  <YAxis dataKey="competence" type="category" width={100} />
                  <Tooltip />
                  <Bar dataKey="demande" fill="#6366f1" name="% des offres" />
                </BarChart>
              </ResponsiveContainer>
              <div className="mt-4 p-4 bg-indigo-50 rounded-lg">
                <p className="text-sm text-gray-700">
                  <strong>💡 Analyse :</strong> Git est la compétence universelle (90% des offres), confirmant 
                  l'importance du travail collaboratif. Python (85%) et JavaScript (78%) dominent les langages, 
                  reflétant la polyvalence recherchée. Les technologies cloud (AWS 65%, Docker 62%) confirment 
                  la transition vers l'infrastructure moderne.
                </p>
              </div>
            </div>

            <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
              <div className="bg-white rounded-lg shadow-md p-6">
                <h3 className="text-xl font-bold mb-4 text-blue-600">Top 5 Langages</h3>
                <div className="space-y-3">
                  {[
                    { lang: 'Python', percent: 85 },
                    { lang: 'JavaScript', percent: 78 },
                    { lang: 'Java', percent: 72 },
                    { lang: 'SQL', percent: 68 },
                    { lang: 'C++', percent: 45 }
                  ].map((item) => (
                    <div key={item.lang}>
                      <div className="flex justify-between mb-1">
                        <span className="font-medium">{item.lang}</span>
                        <span className="text-gray-600">{item.percent}%</span>
                      </div>
                      <div className="w-full bg-gray-200 rounded-full h-2">
                        <div
                          className="bg-blue-600 h-2 rounded-full"
                          style={{ width: `${item.percent}%` }}
                        ></div>
                      </div>
                    </div>
                  ))}
                </div>
              </div>

              <div className="bg-white rounded-lg shadow-md p-6">
                <h3 className="text-xl font-bold mb-4 text-purple-600">Technologies Cloud/DevOps</h3>
                <div className="space-y-3">
                  {[
                    { tech: 'AWS', percent: 65 },
                    { tech: 'Docker', percent: 62 },
                    { tech: 'Kubernetes', percent: 48 },
                    { tech: 'Azure', percent: 42 },
                    { tech: 'CI/CD', percent: 55 }
                  ].map((item) => (
                    <div key={item.tech}>
                      <div className="flex justify-between mb-1">
                        <span className="font-medium">{item.tech}</span>
                        <span className="text-gray-600">{item.percent}%</span>
                      </div>
                      <div className="w-full bg-gray-200 rounded-full h-2">
                        <div
                          className="bg-purple-600 h-2 rounded-full"
                          style={{ width: `${item.percent}%` }}
                        ></div>
                      </div>
                    </div>
                  ))}
                </div>
              </div>
            </div>
          </div>
        )}

        {/* Onglet Géographie */}
        {activeTab === 'geographie' && (
          <div className="space-y-6">
            <div className="bg-white rounded-lg shadow-md p-6">
              <h2 className="text-2xl font-bold mb-4 flex items-center gap-2">
                <MapPin className="text-red-600" />
                Distribution Géographique des Offres
              </h2>
              <p className="text-gray-600 mb-6">
                Concentration des opportunités par ville
              </p>
              <ResponsiveContainer width="100%" height={350}>
                <BarChart data={locationData}>
                  <CartesianGrid strokeDasharray="3 3" />
                  <XAxis dataKey="ville" />
                  <YAxis />
                  <Tooltip />
                  <Bar dataKey="offres" fill="#ef4444" name="Nombre d'offres" />
                </BarChart>
              </ResponsiveContainer>
              <div className="mt-4 p-4 bg-red-50 rounded-lg">
                <p className="text-sm text-gray-700">
                  <strong>💡 Analyse :</strong> Paris concentre 41% des offres (1,450), confirmant sa position 
                  dominante dans l'écosystème tech français. Lyon (580) et Toulouse (420) se distinguent comme 
                  pôles régionaux majeurs. La décentralisation reste limitée avec un rapport de 1 à 5 entre Paris 
                  et les principales métropoles régionales.
                </p>
              </div>
            </div>

            <div className="bg-white rounded-lg shadow-md p-6">
              <h2 className="text-2xl font-bold mb-4">Salaires Moyens par Ville</h2>
              <p className="text-gray-600 mb-6">
                Comparaison des rémunérations selon la localisation
              </p>
              <ResponsiveContainer width="100%" height={350}>
                <LineChart data={locationData}>
                  <CartesianGrid strokeDasharray="3 3" />
                  <XAxis dataKey="ville" />
                  <YAxis />
                  <Tooltip />
                  <Legend />
                  <Line
                    type="monotone"
                    dataKey="salaireMoyen"
                    stroke="#f59e0b"
                    strokeWidth={3}
                    name="Salaire moyen (€)"
                  />
                </LineChart>
              </ResponsiveContainer>
              <div className="mt-4 p-4 bg-orange-50 rounded-lg">
                <p className="text-sm text-gray-700">
                  <strong>💡 Analyse :</strong> Paris offre une prime salariale de 25% par rapport à la moyenne 
                  des autres métropoles (85,000€ vs 68,000€). Cet écart reflète le coût de la vie mais aussi la 
                  concentration d'entreprises tech et de postes à forte valeur ajoutée dans la capitale.
                </p>
              </div>
            </div>
          </div>
        )}

        {/* Conclusion */}
        <div className="bg-gradient-to-r from-gray-800 to-gray-900 rounded-lg shadow-lg p-8 mt-8 text-white">
          <h2 className="text-3xl font-bold mb-6">🎯 Conclusions Clés</h2>
          <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
            <div className="bg-white bg-opacity-10 rounded-lg p-4">
              <h3 className="font-bold text-xl mb-2 text-blue-300">Marché dynamique</h3>
              <p className="text-gray-200 text-sm">
                Croissance de 18% sur 12 mois avec 3,500+ offres analysées. Le CDI reste dominant (72%) 
                mais le freelance progresse (10%).
              </p>
            </div>
            <div className="bg-white bg-opacity-10 rounded-lg p-4">
              <h3 className="font-bold text-xl mb-2 text-green-300">Rémunérations attractives</h3>
              <p className="text-gray-200 text-sm">
                Salaire médian de 78,000€ avec des pics à 95,000€ pour l'IA/ML. Forte progression avec 
                l'expérience (+150% de 0 à 15+ ans).
              </p>
            </div>
            <div className="bg-white bg-opacity-10 rounded-lg p-4">
              <h3 className="font-bold text-xl mb-2 text-purple-300">Compétences polyvalentes</h3>
              <p className="text-gray-200 text-sm">
                Git (90%), Python (85%) et JavaScript (78%) en tête. Les technologies cloud et DevOps 
                deviennent incontournables (AWS 65%, Docker 62%).
              </p>
            </div>
            <div className="bg-white bg-opacity-10 rounded-lg p-4">
              <h3 className="font-bold text-xl mb-2 text-orange-300">Concentration géographique</h3>
              <p className="text-gray-200 text-sm">
                Paris domine avec 41% des offres et une prime salariale de 25%. Lyon et Toulouse émergent 
                comme alternatives viables.
              </p>
            </div>
          </div>
        </div>

        {/* Footer */}
        <div className="mt-8 text-center text-gray-500 text-sm">
          <p>Analyse réalisée sur la base de données des métiers de l'ingénierie</p>
          <p className="mt-2">Source: Kaggle - Data Analyse des Métiers de l'Ingénierie</p>
        </div>
      </div>
    </div>
  );
};

export default EngineeringJobsAnalysis;
