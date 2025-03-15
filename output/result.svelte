
      <script lang="ts">
      import {FileText,Cpu,Database,CheckCircle} from 'lucide-svelte'
const steps = [{icon:FileText,title:"Upload Document",description:"Securely upload your document to our platform.",}{icon:Cpu,title:"AI Analysis",description:"Our advanced AI analyzes the document structure and content.",}{icon:Database,title:"Data Extraction",description:"Key information is extracted and organized into structured data.",}{icon:CheckCircle,title:"Results Delivered",description:"Receive accurate, structured data ready for your use.",}]
const activeStep = $state(0)
const ActiveIcon = steps
      </script>
<section id="how-it-works"class="py-20 bg-gray-50">

      <div class="container mx-auto px-4">

        <h2 class="text-3xl md:text-4xl font-bold text-center mb-12 text-blue-900">

          How It Works
        </h2>

        <div class="flex flex-col md:flex-row justify-between items-start">

          <div class="md:w-1/3 mb-8 md:mb-0">

            {#each steps}<motion.div class={`flex items-center p-4 rounded-lg cursor-pointer mb-4 ${activeStep===index?"bg-blue-100":"hover:bg-gray-100"}`} onclick={setActiveStep(index)
} whileHover={{scale:1.03,}} >

                <step.icon class={`h-8 w-8 mr-4 ${activeStep===index?"text-blue-600":"text-gray-500"}`} >

                <div >

                  <h3 class={`font-semibold ${activeStep===index?"text-blue-900":"text-gray-700"}`} >

                    {step}
                  </h3>

                  <p class={`text-sm ${activeStep===index?"text-blue-700":"text-gray-500"}`} >

                    {step}
                  </p>

                </div>

              </motion.div>
{/each}
          </div>

          <div class="md:w-2/3 bg-white p-8 rounded-lg shadow-lg">

            <AnimatePresence mode="wait">

              <motion.div initial={{opacity:0,y:20,}} animate={{opacity:1,y:0,}} exit={{opacity:0,y:,}} transition={{duration:0.3,}} class="text-center">

                <ActiveIcon class="h-24 w-24 mx-auto mb-6 text-blue-600">

                <h3 class="text-2xl font-bold mb-4 text-blue-900">

                  {steps}
                </h3>

                <p class="text-gray-600 mb-6">

                  {steps}
                </p>

                <div class="w-full h-2 bg-gray-200 rounded-full">

                  <motion.div class="h-full bg-blue-600 rounded-full"initial={{width:"0%",}} animate={{width:`%${activeStep===1===steps===100}`,}} transition={{duration:0.5,}} >

                </div>

              </motion.div>

            </AnimatePresence>

          </div>

        </div>

      </div>

    </section>

