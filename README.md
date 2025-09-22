  {/* Login Modal */}
  {showLogin && (
    <div className="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50">
      <Card className="w-96">
        <CardHeader>
          <CardTitle>Login Admin</CardTitle>
          <CardDescription>Masukkan username dan password untuk akses admin</CardDescription>
        </CardHeader>
        <CardContent className="space-y-4">
          <div className="space-y-2">
            <Label htmlFor="username">Username</Label>
            <Input 
              id="username" 
              value={username} 
              onChange={(e) => setUsername(e.target.value)} 
              placeholder="Buton Heritage" 
            />
          </div>
          <div className="space-y-2">
            <Label htmlFor="password">Password</Label>
            <Input 
              id="password" 
              type="password" 
              value={password} 
              onChange={(e) => setPassword(e.target.value)} 
              placeholder="1q2w3e4r5t6y" 
            />
          </div>
          <div className="flex justify-between pt-4">
            <Button variant="outline" onClick={() => setShowLogin(false)}>Batal</Button>
            <Button onClick={handleLogin}>Login</Button>
          </div>
        </CardContent>
      </Card>
    </div>
  )}

  <main className="container mx-auto px-4 py-8">
    {/* Home Section */}
    {activeSection === "home" && (
      <section className="space-y-12">
        <div className="relative rounded-xl overflow-hidden shadow-lg">
          <img 
            src="https://placeholder-image-service.onrender.com/image/1200x400?prompt=Traditional%20Buton%20culture%20showcasing%20dance%2C%20artifacts%2C%20and%20landscapes&id=6f7g8h9i-0j1k-2l3m-4n5o-6p7q8r9s0t1u" 
            alt="Budaya Buton dengan tarian, artefak, dan lanskap indah" 
            className="w-full h-64 md:h-96 object-cover"
          />
          <div className="absolute inset-0 bg-gradient-to-t from-black to-transparent opacity-70"></div>
          <div className="absolute bottom-0 left-0 right-0 p-8 text-white">
            <h2 className="text-3xl md:text-4xl font-bold mb-4">Selamat Datang di Yayasan Buton Heritage</h2>
            <p className="text-lg max-w-2xl">Lembaga pelestarian budaya benda dan takbenda untuk menjaga warisan leluhur Buton</p>
          </div>
        </div>

        <div className="grid grid-cols-1 md:grid-cols-3 gap-6 mt-12">
          <Card className="text-center hover:shadow-xl transition-shadow">
            <CardHeader>
              <CardTitle className="text-blue-800">Kegiatan</CardTitle>
            </CardHeader>
            <CardContent>
              <p>Jelajahi berbagai kegiatan pelestarian budaya yang kami selenggarakan</p>
              <Button onClick={() => setActiveSection("activities")} className="mt-4 bg-blue-600 hover:bg-blue-700">Lihat Kegiatan</Button>
            </CardContent>
          </Card>

          <Card className="text-center hover:shadow-xl transition-shadow">
            <CardHeader>
              <CardTitle className="text-red-600">Hasil</CardTitle>
            </CardHeader>
            <CardContent>
              <p>Lihat dokumentasi dan hasil dari berbagai kegiatan yang telah dilakukan</p>
              <Button onClick={() => setActiveSection("results")} className="mt-4 bg-red-600 hover:bg-red-700">Lihat Hasil</Button>
            </CardContent>
          </Card>

          <Card className="text-center hover:shadow-xl transition-shadow">
            <CardHeader>
              <CardTitle className="text-amber-700">Tulisan</CardTitle>
            </CardHeader>
            <CardContent>
              <p>Baca tulisan dan artikel tentang budaya, sejarah, dan tradisi Buton</p>
              <Button onClick={() => setActiveSection("articles")} className="mt-4 bg-amber-600 hover:bg-amber-700">Baca Tulisan</Button>
            </CardContent>
          </Card>
        </div>
      </section>
    )}

    {/* Vision & Mission Section */}
    {activeSection === "vision" && (
      <section className="space-y-8">
        <h2 className="text-3xl font-bold text-center text-blue-800 mb-8">Visi & Misi</h2>
        
        <Card className="bg-blue-50 border-blue-200">
          <CardHeader>
            <CardTitle className="text-blue-800">Visi</CardTitle>
          </CardHeader>
          <CardContent>
            <p className="text-lg">Menjadikan Buton Heritage sebagai pelopor gerakan pelestarian budaya, sosial, dan lingkungan di Kepulauan Buton melalui penguatan identitas lokal, edukasi publik, aksi pelestarian, dan kolaborasi berkelanjutan, yang berlandaskan nilai kearifan lokal.</p>
          </CardContent>
        </Card>

        <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
          <Card>
            <CardHeader>
              <CardTitle className="text-red-600">1. Pelestarian Budaya</CardTitle>
            </CardHeader>
            <CardContent>
              <p>Melestarikan dan mendokumentasikan warisan budaya benda dan takbenda Buton.</p>
            </CardContent>
          </Card>

          <Card>
            <CardHeader>
              <CardTitle className="text-red-600">2. Pemberdayaan Sosial</CardTitle>
            </CardHeader>
            <CardContent>
              <p>Memberdayakan masyarakat melalui program berbasis kearifan lokal.</p>
            </CardContent>
          </Card>

          <Card>
            <CardHeader>
              <CardTitle className="text-red-600">3. Pelestarian Lingkungan</CardTitle>
            </CardHeader>
            <CardContent>
              <p>Menjaga kelestarian lingkungan sebagai bagian dari warisan budaya.</p>
            </CardContent>
          </Card>

          <Card>
            <CardHeader>
              <CardTitle className="text-red-600">4. Aksi Lapangan</CardTitle>
            </CardHeader>
            <CardContent>
              <p>Melakukan kegiatan langsung di lapangan untuk pelestarian budaya.</p>
            </CardContent>
          </Card>

          <Card className="md:col-span-2">
            <CardHeader>
              <CardTitle className="text-red-600">5. Promosi dan Kemitraan</CardTitle>
            </CardHeader>
            <CardContent>
              <p>Memperluas jejaring dan mempromosikan budaya Buton melalui kemitraan strategis.</p>
            </CardContent>
          </Card>
        </div>
      </section>
    )}

    {/* Activities Section */}
    {activeSection === "activities" && (
      <section className="space-y-8">
        <div className="flex justify-between items-center">
          <h2 className="text-3xl font-bold text-blue-800">Kegiatan</h2>
          {isLoggedIn && (
            <Button onClick={addNewActivity} className="bg-green-600 hover:bg-green-700">Tambah Kegiatan</Button>
          )}
        </div>
        
        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          {activities.map((activity) => (
            <Card key={activity.id} className="overflow-hidden hover:shadow-xl transition-shadow">
              <div className="h-48 overflow-hidden">
                <img 
                  src={activity.image} 
                  alt={activity.title}
                  className="w-full h-full object-cover"
                />
              </div>
              <CardHeader>
                <CardTitle>{activity.title}</CardTitle>
                <CardDescription>{activity.description}</CardDescription>
              </CardHeader>
            </Card>
          ))}
        </div>
      </section>
    )}

    {/* Results Section */}
    {activeSection === "results" && (
      <section className="space-y-8">
        <div className="flex justify-between items-center">
          <h2 className="text-3xl font-bold text-blue-800">Hasil Kegiatan</h2>
          {isLoggedIn && (
            <Button onClick={addNewResult} className="bg-green-600 hover:bg-green-700">Tambah Hasil</Button>
          )}
        </div>
        
        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          {results.map((result) => (
            <Card key={result.id} className="overflow-hidden hover:shadow-xl transition-shadow">
              <div className="h-48 overflow-hidden">
                <img 
                  src={result.image} 
                  alt={result.title}
                  className="w-full h-full object-cover"
                />
              </div>
              <CardHeader>
                <CardTitle>{result.title}</CardTitle>
                <CardDescription>{result.description}</CardDescription>
              </CardHeader>
            </Card>
          ))}
        </div>
      </section>
    )}

    {/* Articles Section */}
    {activeSection === "articles" && (
      <section className="space-y-8">
        <div className="flex justify-between items-center">
          <h2 className="text-3xl font-bold text-blue-800">Tulisan</h2>
          {isLoggedIn && (
            <Button onClick={addNewArticle} className="bg-green-600 hover:bg-green-700">Tambah Tulisan</Button>
          )}
        </div>
        
        <div className="grid grid-cols-1 gap-6">
          {articles.map((article) => (
            <Card key={article.id} className="hover:shadow-xl transition-shadow">
              <CardHeader>
                <div className="flex justify-between items-start">
                  <CardTitle>{article.title}</CardTitle>
                  <span className="bg-blue-100 text-blue-800 text-xs font-medium px-2.5 py-0.5 rounded">
                    {article.category}
                  </span>
                </div>
              </CardHeader>
              <CardContent>
                <p>{article.content}</p>
              </CardContent>
            </Card>
          ))}
        </div>
      </section>
    )}

    {/* About Us Section */}
    {activeSection === "about" && (
      <section className="space-y-8">
        <h2 className="text-3xl font-bold text-blue-800">Tentang Kami</h2>
        
        <Card>
          <CardHeader>
            <CardTitle>Sejarah Yayasan Buton Heritage</CardTitle>
          </CardHeader>
          <CardContent className="space-y-4">
            <p>Yayasan Buton Heritage didirikan pada tahun 2010 dengan tujuan melestarikan warisan budaya Buton yang kaya dan beragam. Sejak berdirinya, yayasan telah aktif dalam berbagai kegiatan pelestarian budaya baik benda maupun takbenda.</p>
            <p>Kami percaya bahwa melestarikan warisan leluhur adalah tanggung jawab bersama untuk menjaga identitas dan jati diri bangsa.</p>
          </CardContent>
        </Card>

        <Card>
          <CardHeader>
            <CardTitle>Struktur Organisasi</CardTitle>
          </CardHeader>
          <CardContent>
            <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
              <div>
                <h3 className="font-semibold text-lg mb-2">Dewan Pembina</h3>
                <ul className="list-disc list-inside">
                  <li>Dr. Ahmad Suryadi, M.Hum. - Ketua</li>
                  <li>Prof. Dr. Maria Ulfa, M.A. - Anggota</li>
                  <li>Drs. Hasan Basri - Anggota</li>
                </ul>
              </div>
              <div>
                <h3 className="font-semibold text-lg mb-2">Tim Pelaksana</h3>
                <ul className="list-disc list-inside">
                  <li>Muhammad Ridwan, S.S. - Direktur</li>
                  <li>Siti Aminah, S.Hum. - Koordinator Program</li>
                  <li>Abdul Rahman, S.Sn. - Koordinator Dokumentasi</li>
                </ul>
              </div>
            </div>
          </CardContent>
        </Card>

        <Card>
          <CardHeader>
            <CardTitle>Kontak Kami</CardTitle>
          </CardHeader>
          <CardContent>
            <div className="space-y-2">
              <p><strong>Alamat:</strong> Jl. Sultan Hasanuddin No. 45, Baubau, Sulawesi Tenggara</p>
              <p><strong>Telepon:</strong> (0402) 123456</p>
              <p><strong>Email:</strong> info@butonheritage.org</p>
            </div>
          </CardContent>
        </Card>
      </section>
    )}
  </main>

  <footer className="bg-blue-800 text-white py-8 mt-12">
    <div className="container mx-auto px-4">
      <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div>
          <h3 className="text-xl font-bold mb-4">Yayasan Buton Heritage</h3>
          <p>Melestarikan warisan budaya Buton untuk generasi mendatang.</p>
        </div>
        <div>
          <h3 className="text-xl font-bold mb-4">Tautan Cepat</h3>
          <ul className="space-y-2">
            <li><button onClick={() => setActiveSection("home")} className="hover:underline">Home</button></li>
            <li><button onClick={() => setActiveSection("activities")} className="hover:underline">Kegiatan</button></li>
            <li><button onClick={() => setActiveSection("articles")} className="hover:underline">Tulisan</button></li>
            <li><button onClick={() => setActiveSection("about")} className="hover:underline">Tentang Kami</button></li>
          </ul>
        </div>
        <div>
          <h3 className="text-xl font-bold mb-4">Hubungi Kami</h3>
          <p>Jl. Sultan Hasanuddin No. 45, Baubau</p>
          <p>Sulawesi Tenggara, Indonesia</p>
          <p className="mt-2">info@butonheritage.org</p>
        </div>
      </div>
      <div className="border-t border-blue-700 mt-8 pt-6 text-center">
        <p>© 2023 Yayasan Buton Heritage. All rights reserved.</p>
      </div>
    </div>
  </footer>
</div># BUTONHERITAGE4
