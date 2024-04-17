# Modal-page
"use client";
import Modal from "@/components/Modal";
import { useState } from "react";

export default function Home() {
  const [showModal, setShowModal] = useState(false);
  const [showModal1, setShowModal1] = useState(false);
  return (
    <main className="flex min-h-screen flex-col items-center  p-24">
      <div className="mb-10">Creating Modal Page</div>
      <div className=" flex gap-6">
        <button
          className="bg-pink-500 text-white text-lg px-4 py-2 font-sans focus:outline-1 rounded-xl"
          onClick={() => setShowModal(true)}
        >
          Text Modal
        </button>
        <button className="bg-pink-500 text-white text-lg px-4 py-2 font-sans focus:outline-1 rounded-xl">
          Video Modal
        </button>
        <button
          className="bg-pink-500 text-white text-lg px-4 py-2 font-sans focus:outline-1 rounded-xl"
          onClick={() => setShowModal1(true)}
        >
          Form Modal
        </button>
      </div>
      <Modal isVisible={showModal} onClose={() => setShowModal(false)}>
        <div className="p-6 gap-5 flex flex-col">
          <h1 className="text-lg font-bold">Modal Title</h1>
          <p>
            The Menu component uses the Popover component internally. However,
            you might want to use a different positioning strategy, or not
            blocking the scroll. For answering those needs, we expose a MenuList
            component that you can compose, with Popper in this example. The
            primary responsibility of the MenuList component is to handle the
            focus.
          </p>
        </div>
      </Modal>
      <Modal isVisible={showModal1} onClose={() => setShowModal1(false)}>
        <div className=" ">
          <form className=" p-8 bg-white rounded-lg shadow-md">
            <h2 className="text-2xl font-semibold text-gray-800 mb-4">
              Sign Up
            </h2>
            <div className="mb-4">
              <label
                htmlFor="email"
                className="block text-gray-700 font-semibold mb-2"
              >
                Email Address
              </label>
              <input
                type="email"
                id="email"
                name="email"
                className="w-full px-3 py-2 border rounded-md focus:outline-none focus:border-blue-500"
              />
            </div>
            <div className="mb-4">
              <label
                htmlFor="password"
                className="block text-gray-700 font-semibold mb-2"
              >
                Password
              </label>
              <input
                type="password"
                id="password"
                name="password"
                className="w-full px-3 py-2 border rounded-md focus:outline-none focus:border-blue-500"
              />
            </div>
            <div className="mb-6">
              <label
                htmlFor="confirmPassword"
                className="block text-gray-700 font-semibold mb-2"
              >
                Confirm Password
              </label>
              <input
                type="password"
                id="confirmPassword"
                name="confirmPassword"
                className="w-full px-3 py-2 border rounded-md focus:outline-none focus:border-blue-500"
              />
            </div>
            <button
              type="submit"
              className="w-full bg-blue-500 text-white py-2 px-4 rounded-md hover:bg-blue-600 transition-colors duration-300"
            >
              Sign Up
            </button>
          </form>
        </div>
      </Modal>
    </main>
  );
}







export default function Modal({ isVisible, onClose, children }) {
  if (!isVisible) return null;
  return (
    <div className="items-center justify-center flex bg-black bg-opacity-25 backdrop-blur-sm fixed inset-0">
      <div className="w-[600px] flex flex-col">
        <button
          className="place-self-end text-white text-xl"
          onClick={() => onClose()}
        >
          X
        </button>
        <div className="bg-white rounded-sm p-2 ">{children}</div>
      </div>
    </div>
  );
}

