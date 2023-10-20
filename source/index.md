---
layout: welcome
title: Script Renderer
cover: false
---

<script src="https://unpkg.com/dropzone@5/dist/min/dropzone.min.js"></script>

<script src="/assets/script/custom.js"></script>

<script defer src="/assets/script/script.js"></script>
<script defer src="https://unpkg.com/@popperjs/core@2"></script>
<script defer src="https://unpkg.com/tippy.js@6"></script>

{% include config-with-checks.html %}

<div
  class="alert alert-info"
  role="alert"
  id="userWarning"
>
This site is being rearchitected behind the scenes. Apologies for any unexpected
behaviour or downtime.
</div>

<div class="alert alert-danger">I've broken the API call somehow (CORS is back baby!) - under investigation</div>

<div class="container">
  <div class="article">
    <div>
      Drag your
      <a
        href="https://script.bloodontheclocktower.com/"
        target="script.botf"
        >custom script</a
      >
      json file here to upload it to the server. After a few seconds you
      should receive the generated PDF.
    </div>
  </div>
  <div class="section">
    <div id="scriptzone">
      <form
        class="dropzone needsclick"
        id="customScript"
        name="customScript"
      >
        <div class="ul-options">
          <details open>
            <summary>Script Options</summary>

            <div class="script-option">
              <div>Paper size:</div>
              <select name="paperSize" id="paperSize">
                <option value="A4" selected>A4</option>
                <option value="letter">Letter</option>
              </select>
              <img
                src="/assets/img/infobutton.png"
                alt="info"
                height="16"
                class="tippy-tip"
                data-tippy-content="Choose your preferred paper size: <code>A4</code> or <code>Letter</code>.<br/><small><em>Letter has not been fully tested and refined so may yield unexpected results.</em></small>"
              />
            </div>

            <div class="script-option">
              <div>Night Info:</div>
              <select name="stNightInfo" id="stNightInfo">
                <option value="onesheet">One Sheet</option>
                <option value="twosheet" selected>Two Sheets</option>
              </select>
              <img
                src="/assets/img/infobutton.png"
                alt="info"
                height="16"
                class="tippy-tip"
                data-tippy-content="<strong>One Sheet</strong> generates a single page for the Night Information. There are no descriptions of the actions to perform, simply a list of phases (<em>Dusk, Dawn, … characters, …</em>)<br/><br/><strong>Two Sheets</strong> generates one page for each of <em>First Night</em> and <em>Second Night</em> and has the actions to perform for each phase. Generally expected to be printed double-sided."
              />
            </div>

            <div class="script-option">
              <div>Format:</div>
              <select name="scriptFormat" id="scriptFormat">
                <option value="regular">Regular</option>
                <option value="sample" selected>Enhanced</option>
                <option value="easyprint">Hassle-Free Printable</option>
              </select>
              <img
                src="/assets/img/infobutton.png"
                alt="info"
                height="16"
                class="tippy-tip"
                data-tippy-content="<strong>Regular</strong> format is the default format and is a single page for each page of information (Player Reference, Night Order, etc).<br/><br/><strong>Enhanced</strong> format is a short step up from regular, and includes a compact version of the night order. This could be printed double-sided with the player references.<br/><br/><strong>Hassle-Free Printable</strong> format is intended to be a document that can just be printed and has the correct quantity of pages for players as well as the Storyteller.<br><br>Both non-regular options enable other PDF rendering options such as <em>double-sided printing</em>."
              />
            </div>

            <div class="script-option">
              <div>Print Format:</div>
              <select
                name="printFormat"
                id="printFormat"
                class="needs-easyprint"
              >
                <option value="singleSided">Single-Sided</option>
                <option value="doubleSided" selected>Double-Sided</option>
              </select>
              <img
                src="/assets/img/infobutton.png"
                alt="info"
                height="16"
                class="tippy-tip"
                data-tippy-content="Choose your preferred print format: <code>Single-Sided</code> or <code>Double-Sided</code>.<br/><br/>Depending on other options selected this will insert blank pages, or 'one sheet' style Night Info, where necessary to ensure the correct pages are printed on the front and back of each sheet."
              />
            </div>

            <div class="script-option">
              <div>Players see Night Info:</div>
              <select
                name="playerNightInfo"
                id="playerNightInfo"
                class="needs-easyprint"
              >
                <option value="yes">Yes, share with players</option>
                <option value="no" selected>No, keep it vague</option>
              </select>
              <img
                src="/assets/img/infobutton.png"
                alt="info"
                height="16"
                class="tippy-tip"
                data-tippy-content="Some Storytellers like to share the Night Info with players, others prefer to keep it vague. Choose your preference here.<br/><br/>If you choose to share the Night Info with players, the generated PDF will have the Night Info pages included. If you choose to keep it vague, the Night Info pages will be omitted from the generated PDF and a blank page will be generated in their place.<br/><br/><strong>Note:</strong> This option is only available when <em>Double-Sided</em> print format is selected."
              />
            </div>

            <div class="script-option">
              <div>Player Count:</div>
              <select
                name="playerCount"
                id="playerCount"
                class="needs-easyprint"
              >
                <option value="teensyville">
                  Teensyville (7 copies)
                </option>
                <option value="ravenswood_regular" selected>
                  Ravenswood Bluff (16 copies)
                </option>
                <option value="ravenswood_traveler">
                  Ravenswood Bluff Max (21 copies)
                </option>
                <option value="sample">
                  Non-regular format (1 copy)
                </option>
              </select>
              <img
                src="/assets/img/infobutton.png"
                alt="info"
                height="16"
                class="tippy-tip"
                data-tippy-content="There's no benefit in printing more copies than you need. Choose the number of players you expect to have in your game and the generated PDF will have the correct number of pages for you to print.<br/><br/><strong>Teensyville</strong>: these are games and scripts suited for 5 and 6 players. <small><em>(7 copies)</em></small> <br/><strong>Ravenswood Bluff</strong>: there are enough copies to run games at the full non-traveler player count. Alternatively medium sized towns with space for travellers. <small><em>(16 copies)</em></small> <br/><strong>Ravenswood Bluff Max</strong>: enough copies for a full village and the maximum number of travelers. <small><em>(21 copies)</em></small><br/><strong>Non-regular format:</strong> this is a slightly weird option for those that want to showcase some of the 'Hassle-Free' options and only produce one copy with the extended options enabled.<br/><br/><strong>… one for the Storyteller</strong>: each quantity is one more than you may initially expect so that the Storyteller has a copy to refer to. <br/><br/><strong>Note:</strong> This option is only available when <em>Hassle-Free Printable</em> format is selected."
              />
            </div>
          </details>
        </div>
        <div class="dz-message needsclick">
          <strong>Drop files here or click to upload.</strong><br />
          <small
            >Choose your options above before uploading.<br />
            Uploads are immediately processed.</small
          >
        </div>
      </form>
    </div>

  </div>

    <div id="preview-template" style="display: none">
      <div class="dz-preview dz-file-preview">
        <div class="dz-image"><img data-dz-thumbnail="" /></div>
        <div class="dz-details">
          <div class="dz-size"><span data-dz-size=""></span></div>
          <div class="dz-filename"><span data-dz-name=""></span></div>
        </div>
        <div class="dz-progress">
          <span class="dz-upload" data-dz-uploadprogress=""></span>
        </div>
        <div class="dz-error-message">
          <span data-dz-errormessage=""></span>
        </div>
        <div class="dz-success-mark">
          <svg
            width="54px"
            height="54px"
            viewBox="0 0 54 54"
            version="1.1"
            xmlns="http://www.w3.org/2000/svg"
            xmlns:xlink="http://www.w3.org/1999/xlink"
            xmlns:sketch="http://www.bohemiancoding.com/sketch/ns"
          >
            <title>Check</title>
            <desc>Created with Sketch.</desc>
            <g
              id="Page-1"
              stroke="none"
              stroke-width="1"
              fill="none"
              fill-rule="evenodd"
              sketch:type="MSPage"
            >
              <path
                d="M23.5,31.8431458 L17.5852419,25.9283877 C16.0248253,24.3679711 13.4910294,24.366835 11.9289322,25.9289322 C10.3700136,27.4878508 10.3665912,30.0234455 11.9283877,31.5852419 L20.4147581,40.0716123 C20.5133999,40.1702541 20.6159315,40.2626649 20.7218615,40.3488435 C22.2835669,41.8725651 24.794234,41.8626202 26.3461564,40.3106978 L43.3106978,23.3461564 C44.8771021,21.7797521 44.8758057,19.2483887 43.3137085,17.6862915 C41.7547899,16.1273729 39.2176035,16.1255422 37.6538436,17.6893022 L23.5,31.8431458 Z M27,53 C41.3594035,53 53,41.3594035 53,27 C53,12.6405965 41.3594035,1 27,1 C12.6405965,1 1,12.6405965 1,27 C1,41.3594035 12.6405965,53 27,53 Z"
                id="Oval-2"
                stroke-opacity="0.198794158"
                stroke="#747474"
                fill-opacity="0.816519475"
                fill="#FFFFFF"
                sketch:type="MSShapeGroup"
              ></path>
            </g>
          </svg>
        </div>
        <div class="dz-error-mark">
          <svg
            width="54px"
            height="54px"
            viewBox="0 0 54 54"
            version="1.1"
            xmlns="http://www.w3.org/2000/svg"
            xmlns:xlink="http://www.w3.org/1999/xlink"
            xmlns:sketch="http://www.bohemiancoding.com/sketch/ns"
          >
            <title>error</title>
            <desc>Created with Sketch.</desc>
            <defs></defs>
            <g
              id="Page-1"
              stroke="none"
              stroke-width="1"
              fill="none"
              fill-rule="evenodd"
              sketch:type="MSPage"
            >
              <g
                id="Check-+-Oval-2"
                sketch:type="MSLayerGroup"
                stroke="#747474"
                stroke-opacity="0.198794158"
                fill="#FFFFFF"
                fill-opacity="0.816519475"
              >
                <path
                  d="M32.6568542,29 L38.3106978,23.3461564 C39.8771021,21.7797521 39.8758057,19.2483887 38.3137085,17.6862915 C36.7547899,16.1273729 34.2176035,16.1255422 32.6538436,17.6893022 L27,23.3431458 L21.3461564,17.6893022 C19.7823965,16.1255422 17.2452101,16.1273729 15.6862915,17.6862915 C14.1241943,19.2483887 14.1228979,21.7797521 15.6893022,23.3461564 L21.3431458,29 L15.6893022,34.6538436 C14.1228979,36.2202479 14.1241943,38.7516113 15.6862915,40.3137085 C17.2452101,41.8726271 19.7823965,41.8744578 21.3461564,40.3106978 L27,34.6568542 L32.6538436,40.3106978 C34.2176035,41.8744578 36.7547899,41.8726271 38.3137085,40.3137085 C39.8758057,38.7516113 39.8771021,36.2202479 38.3106978,34.6538436 L32.6568542,29 Z M27,53 C41.3594035,53 53,41.3594035 53,27 C53,12.6405965 41.3594035,1 27,1 C12.6405965,1 1,12.6405965 1,27 C1,41.3594035 12.6405965,53 27,53 Z"
                  id="Oval-2"
                  sketch:type="MSShapeGroup"
                ></path>
              </g>
            </g>
          </svg>
        </div>
