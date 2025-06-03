import { useState } from "react"; import { Card, CardContent } from "@/components/ui/card"; import { Button } from "@/components/ui/button"; import { Input } from "@/components/ui/input"; import { Tabs, TabsList, TabsTrigger, TabsContent } from "@/components/ui/tabs";

export default function HalaMadridFanPage() { const [user, setUser] = useState(null);

const handleLogin = () => { setUser({ name: "Madridista" }); };

return ( <div className="min-h-screen bg-gradient-to-br from-blue-500 via-white to-green-200 p-4 text-center"> <header className="text-4xl font-bold text-white mb-6">¡Hala Madrid Por Siempre!</header> {!user ? ( <div className="max-w-sm mx-auto bg-white rounded-2xl p-4 shadow-lg"> <h2 className="text-xl mb-2">Login</h2> <Input placeholder="Username" className="mb-2" /> <Input placeholder="Password" type="password" className="mb-4" /> <Button className="w-full bg-blue-700 text-white" onClick={handleLogin}>Login</Button> </div> ) : ( <Tabs defaultValue="home" className="w-full max-w-5xl mx-auto mt-6"> <TabsList className="grid grid-cols-6 bg-yellow-200 rounded-xl"> <TabsTrigger value="home">Home</TabsTrigger> <TabsTrigger value="about">About</TabsTrigger> <TabsTrigger value="gallery">Gallery</TabsTrigger> <TabsTrigger value="comments">Comments</TabsTrigger> <TabsTrigger value="schedule">Schedule</TabsTrigger> <TabsTrigger value="players">Players</TabsTrigger> </TabsList>

<TabsContent value="home">
        <Card className="mt-4">
          <CardContent className="p-6">
            <h2 className="text-2xl font-bold mb-4">Welcome, {user.name}!</h2>
            <p>
              This fan page is dedicated to Real Madrid, the greatest football club in history.
              Relive legendary moments, watch iconic goals, and share the passion with fellow Madridistas.
            </p>
          </CardContent>
        </Card>
      </TabsContent>

      <TabsContent value="about">
        <Card className="mt-4">
          <CardContent className="p-6">
            <h2 className="text-2xl font-bold mb-4">About Real Madrid</h2>
            <p>
              Real Madrid Club de Fútbol, founded in 1902, is renowned for its unmatched success in football.
              With a record number of UEFA Champions League titles and La Liga triumphs, the club is home to legends and timeless victories.
            </p>
          </CardContent>
        </Card>
      </TabsContent>

      <TabsContent value="gallery">
        <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 mt-4">
          <img src="https://upload.wikimedia.org/wikipedia/en/5/56/Real_Madrid_CF.svg" alt="Logo" className="rounded-xl shadow-lg" />
          <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d3/Santiago_Bernabeu_Stadium_-_panoramio.jpg/640px-Santiago_Bernabeu_Stadium_-_panoramio.jpg" alt="Stadium" className="rounded-xl shadow-lg" />
          <iframe
            className="rounded-xl shadow-lg"
            width="100%"
            height="200"
            src="https://www.youtube.com/embed/jN6vayDaE3E"
            title="Real Madrid Highlights"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
            allowFullScreen
          ></iframe>
        </div>
      </TabsContent>

      <TabsContent value="comments">
        <Card className="mt-4">
          <CardContent className="p-6 space-y-4">
            <h2 className="text-2xl font-bold">Fan Comments</h2>
            <Input placeholder="Write your comment..." className="mb-2" />
            <Button className="bg-orange-600 text-white">Post Comment</Button>
            <div className="text-left mt-4">
              <p><strong>Fan1:</strong> Hala Madrid! 💪</p>
              <p><strong>Fan2:</strong> Best club in the world! ⚽</p>
            </div>
          </CardContent>
        </Card>
      </TabsContent>

      <TabsContent value="schedule">
        <Card className="mt-4">
          <CardContent className="p-6 space-y-4">
            <h2 className="text-2xl font-bold">Match Schedule</h2>
            <ul className="text-left">
              <li>🗓️ June 5 - Real Madrid vs. Sevilla</li>
              <li>🗓️ June 12 - Real Madrid vs. Barcelona</li>
              <li>🗓️ June 19 - Real Madrid vs. Atlético Madrid</li>
            </ul>
          </CardContent>
        </Card>
      </TabsContent>

      <TabsContent value="players">
        <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 mt-4">
          <Card>
            <CardContent className="p-4">
              <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8c/Vinicius_Junior_2023.jpg/640px-Vinicius_Junior_2023.jpg" alt="Vinicius Jr" className="rounded-xl mb-2" />
              <h3 className="font-bold">Vinícius Júnior</h3>
              <p>Position: Forward</p>
              <p>Nationality: Brazil</p>
            </CardContent>
          </Card>
          <Card>
            <CardContent className="p-4">
              <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/53/Jude_Bellingham_2023.jpg/640px-Jude_Bellingham_2023.jpg" alt="Jude Bellingham" className="rounded-xl mb-2" />
              <h3 className="font-bold">Jude Bellingham</h3>
              <p>Position: Midfielder</p>
              <p>Nationality: England</p>
            </CardContent>
          </Card>
        </div>
      </TabsContent>
    </Tabs>
  )}
</div>

); }

